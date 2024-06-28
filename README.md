The script:
This script does two things, namely it adds a crontab entry and  it polls the crontab entry for zabbix usage.

There are three subcommands you can use in this script\
--set-crontab, this adds a crontab entry that will append a file with the amount of system updates available (can be used on debian based systems or redhat based systems). This only needs to be ran once.\
--get-updates, this tests if the crontab has been run yet and also manually polls the file created by crontab (or creates one if it does not exist).\
updates.upgrade_count, this is the key used by the poller and should not be used normally.

Be sure to give the script the right permissions to be run by the zabbix agent (eg. 777 perms).

The key to be used in zabbix is updates.upgrade_count. Put the config in your /etc/zabbix/zabbix_agent2.d/ directory. The script itself, upgrade-count, should be placed in /usr/local/bin/ (Could be changed manually in the config)
