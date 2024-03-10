Role Name
=========

Setup ZFS automatic snapshots using `zfs-auto-snapshot`.

Requirements
------------

Requires `zfs-auto-snapshot` already installed.

Role Variables
--------------

- `zfs_auto_snapshot_frequent_interval` - The divisor for the cron minute column setting the "frequent" interval. Defaults to ``15``. Equivalent to cron minute ``*/15``.
- `zfs_auto_snapshot_frequent_keep` - The number of "frequent" snapshots to keep. Defaults to ``4``.
- `zfs_auto_snapshot_hourly_keep` - The number of "hourly" snapshots to keep. Defaults to ``24``.
- `zfs_auto_snapshot_daily_keep` - The number of "daily" snapshots to keep. Defaults to ``7``.
- `zfs_auto_snapshot_weekly_keep` - The number of "weekly" snapshots to keep. Defaults to ``4``.
- `zfs_auto_snapshot_monthly_keep` - The number of "monthly" snapshots to keep. Defaults to ``3``.

Dependencies
------------

None.

Example Playbook
----------------

Setup `zfs-auto-snapshot` with all defaults.

    - hosts: servers
      roles:
         - role: haxwithaxe.zfs_auto_snapshot

License
-------

GPL

Author Information
------------------

Created by [haxwithaxe](https://github.com/haxwithaxe).
