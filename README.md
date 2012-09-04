ts3-munin-py
============

A munin monitoring plugin for Teamspeak3 using Python.

Config
------

Append

[teamspeak3*]
env.teamspeak_query_user serveradmin
env.teamspeak_query_user_password *******
env.teamspeak_host localhost
env.teamspeak_port 10011

to 

/etc/munin/plugin-conf.d/munin-node

