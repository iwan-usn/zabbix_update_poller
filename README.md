crontab
0 0 * * * dnf check-update | grep -Ec ' *updates' > /tmp/upgrade_count

Crontab dat bij upgrade-count hoort
Dit draait 1x per dag om 00:00, dit check alle packages voor upgrades

Be sure to give the files the right permissions for your scenario or it might not work.
