---
transition: none
---

# [Backup]{style="color: green;"} homelab app data

🎯 Let's not lose data in case of a disk failure

* Assemble RAID disk array
    + Example:
        + RAID6
        + 5 `1TB` HDD disks
        + 2 disk failure tolerance
* Use NAS vendor raid solution or [mdadm](https://wiki.debian.org/mdadm)
* Serve raid array using NFS

<br>

Mount NFS, store app data on NFS mount

---
hideInToc: true
transition: none
---

# [Backup]{style="color: green;"} homelab app data

* Use [restic](https://restic.net)
    + Backup to NAS
    + Also backup to cloud storage (Google drive) using `rclone` as restic
        backend
* Run in docker container, using periodic scheduler in each homelab server

```sh
for each app; do
    docker container stop $app
    restic-backup.sh $app
    docker container start $app
done
```

```toml
cron_schedule = "0 3 * * *"  # Every day at 3 AM
run_on_startup = true
ntfy_send_success_notifications = true

[apps.caddy]
container_name = "caddy"
data_dirs = ["caddy/conf", "caddy/site"]
data_dir_root = "/home/berger/data/service_data/"

...
```

---
layout: two-cols-header
layoutClass: gap-8
hideInToc: true
transition: none
---

# [Backup]{style="color: green;"} homelab app data

Alternative: Use bash script, tar + gpg app data

Backup whole docker data mount, daily, with `systemd.timer`s, systemd service
and bash scripts

::left::

##### File: /etc/systemd/system/backup@radicale.timer

```ini
[Unit]
Description=Timer for backing up radicale
[Timer]
OnCalendar=03:30
Persistent=false
[Install]
WantedBy=timers.target
```

##### File: /etc/sytemd/system/backup@.service

```ini
[Unit]
Description=%i: Backup data
[Service]
Type=oneshot
ExecStart=/home/berger/dotfiles/bash_scripts/backup/backup-%i.sh
User=berger
Group=berger
```

::right::

##### File: backup-radicale.sh

```bash
#!/usr/bin/env bash
export APP_NAME="radicale"
export THIS_SCRIPT_NAME=$(basename ${BASH_SOURCE[0]})
# export TO_EXCLUDE=""

THIS_DIR=$(dirname ${BASH_SOURCE[0]})

# delegate to the backup-docker-container-app.sh script
$THIS_DIR/backup-docker-container-app.sh
```

##### File: backup-docker-container-app.sh

```bash
...
tar -czf "$ARCHIVE_PATH" --directory="$DIR_TO_BACKUP" --exclude ...
gpg --encrypt --recipient "Nikos Koukis"
shred --remove ...
...
```

---
hideInToc: true
---

# [Backup]{style="color: green;"} homelab app data
Alternative: Use bash script, tar + gpg app data

List all homelab timers

<div style="gap: 1rem;">
```bash
#!/usr/bin/env bash
set -ex
grep --color=auto -H OnCalendar /etc/systemd/system/backup@*.timer | sort -t = -k2
```
</div>


```console
/etc/systemd/system/backup@caddy.timer:OnCalendar=00:00
/etc/systemd/system/backup@mealie.timer:OnCalendar=00:30
/etc/systemd/system/backup@vaultwarden.timer:OnCalendar=01:00
/etc/systemd/system/backup@calibre-web.timer:OnCalendar=01:30
/etc/systemd/system/backup@vikunja.timer:OnCalendar=02:00
/etc/systemd/system/backup@grocy.timer:OnCalendar=02:30
/etc/systemd/system/backup@transmission-openvpn.timer:OnCalendar=03:00
/etc/systemd/system/backup@radicale.timer:OnCalendar=03:30
/etc/systemd/system/backup@jellyfin.timer:OnCalendar=04:00
/etc/systemd/system/backup@babybuddy.timer:OnCalendar=04:30
/etc/systemd/system/backup@filebrowser.timer:OnCalendar=05:00
/etc/systemd/system/backup@mumble.timer:OnCalendar=05:30
/etc/systemd/system/backup@dockge.timer:OnCalendar=06:00
/etc/systemd/system/backup@trilium.timer: OnCalendar=06:30
```
