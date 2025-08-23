zfs-auto-snapshot
=================

Setup ZFS automatic snapshots using `zfs-auto-snapshot`.

Requirements
------------

Requires `zfs-auto-snapshot` already installed.

Role Variables
--------------

- `zfs_auto_snapshot_frequent_interval` - The divisor for the cron minute column setting the "frequent" interval. Defaults to ``15``. Equivalent to cron minute ``*/15``.
- `zfs_auto_snapshot_frequent_keep` (optional) - The number of "frequent" snapshots to keep. Defaults to ``4``.
- `zfs_auto_snapshot_hourly_keep` (optional) - The number of "hourly" snapshots to keep. Defaults to ``24``.
- `zfs_auto_snapshot_daily_keep` (optional) - The number of "daily" snapshots to keep. Defaults to ``7``.
- `zfs_auto_snapshot_weekly_keep` (optional) - The number of "weekly" snapshots to keep. Defaults to ``4``.
- `zfs_auto_snapshot_monthly_keep` (optional) - The number of "monthly" snapshots to keep. Defaults to ``3``.
- `zfs_auto_snapshot_disabled_by_default` (optional) - When true any pool that doesn't have an entry in `zfs_auto_snapshot_config` will have auto-snapshots disabled at the top level. Defaults to `true`.
- `zfs_auto_snapshot_config` - A list of dictionaries with the following keys:
  - `name` - The pool or volume name (eg ``tank/vol0``).
  - `disabled` (optional) - The enabled/disabled state of all auto-snapshots for this volume. Defaults to unset.
  - `frequent` (optional) - See `zfs-auto-snapshot` documentation. Defaults to unset.
  - `daily` (optional) - See `zfs-auto-snapshot` documentation. Defaults to unset.
  - `weekly` (optional) - See `zfs-auto-snapshot` documentation. Defaults to unset.
  - `monthly` (optional) - See `zfs-auto-snapshot` documentation. Defaults to unset.

Dependencies
------------

None.

Example Playbook
----------------

Setup `zfs-auto-snapshot` with ``tank0`` disabled and only weekly and monthly snapshots for ``tank0``.

    - hosts: servers
      roles:
         - role: haxwithaxe.zfs_auto_snapshot
           vars:
             zfs_auto_snapshot_config:
               - name: tank0
                 disabled: yes
               - name: tank0/foo
                 weekly: yes
                 monthly: yes

License
-------

GPLv3

Author Information
------------------

Created by [haxwithaxe](https://github.com/haxwithaxe).
