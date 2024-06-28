# Zabbix update poller
Written by me, iwan also known as dopamine

## What in the world does it do!?!?!?
Glad you asked, its a simple solution for a very simple problem.\
UPDATES! We all do 'm, we all want to monitor them. This simply adds a key you can add to an item in zabbix that allows you to poll the amount of updates you have open every day. I chose to have the crontab run every night at 12AM because why not.  

## The script:
This script does two things, namely it adds a crontab entry and  it polls the crontab entry for zabbix usage.

There are three subcommands you can use in this script\
--set-crontab, this adds a crontab entry that will append a file with the amount of system updates available (can be used on debian based systems or redhat based systems). This only needs to be ran once.\
--get-updates, this tests if the crontab has been run yet and also manually polls the file created by crontab (or creates one if it does not exist).\
updates.upgrade_count, this is the key used by the poller and should not be used normally.

Be sure to give the script the right permissions to be run by the zabbix agent (eg. 777 perms).

The key to be used in zabbix is updates.upgrade_count. Put the config in your /etc/zabbix/zabbix_agent2.d/ directory. The script itself, upgrade-count, should be placed in /usr/local/bin/ (Could be changed manually in the config)

### Usage
<code>getupdates --set-crontab </code> to automatically set the crontab\
<code>getupdates --get-updates </code> to manually run the poll

