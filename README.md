ts3-munin-py
============
A munin monitoring plugin for Teamspeak3 using Python.


License
-------

Copyright (c) 2012, Axel Philipsenburg

All rights reserved.

Redistribution and use in source and binary forms, with or without modification, are permitted provided that the following conditions are met:

Redistributions of source code must retain the above copyright notice, this list of conditions and the following disclaimer.

Redistributions in binary form must reproduce the above copyright notice, this list of conditions and the following disclaimer in the documentation and/or other materials provided with the distribution.

THIS SOFTWARE IS PROVIDED BY THE COPYRIGHT HOLDERS AND CONTRIBUTORS "AS IS" AND ANY EXPRESS OR IMPLIED WARRANTIES, INCLUDING, BUT NOT LIMITED TO, THE IMPLIED WARRANTIES OF MERCHANTABILITY AND FITNESS FOR A PARTICULAR PURPOSE ARE DISCLAIMED. IN NO EVENT SHALL THE COPYRIGHT HOLDER OR CONTRIBUTORS BE LIABLE FOR ANY DIRECT, INDIRECT, INCIDENTAL, SPECIAL, EXEMPLARY, OR CONSEQUENTIAL DAMAGES (INCLUDING, BUT NOT LIMITED TO, PROCUREMENT OF SUBSTITUTE GOODS OR SERVICES; LOSS OF USE, DATA, OR PROFITS; OR BUSINESS INTERRUPTION) HOWEVER CAUSED AND ON ANY THEORY OF LIABILITY, WHETHER IN CONTRACT, STRICT LIABILITY, OR TORT (INCLUDING NEGLIGENCE OR OTHERWISE) ARISING IN ANY WAY OUT OF THE USE OF THIS SOFTWARE, EVEN IF ADVISED OF THE POSSIBILITY OF SUCH DAMAGE.

Install
-------

Copy the teamspeak3 script to a safe location where it won't interfere with package managements. e.g.

    sudo mkdir -p /usr/local/share/munin/plugins
    sudo cp teamspeak3 /usr/local/share/munin/plugins

If your munin installation has set up a munin user, set the permissions accordingly. e.g.

    su chown -R munin:munin /usr/local/share/munin/

This script has two different modes. One displays the total users of all vhosts on your server, the
other one shows the users per channel in individual graphs per vhost.

Both use the same script file and the selection is made via the script's execution name.

To install the users per vhosts mode use:

    ln -sf /usr/local/share/plugins/teamspeak3 /etc/munin/plugins/teamspeak3_vhosts

To install the users per channel per vhosts mode use:

     ln -sf /usr/local/share/plugins/teamspeak3 /etc/munin/plugins/teamspeak3

Make sure to restart munin-node afterwards.

    sudo /etc/init.d/munin-node restart

Config
------

Append

    [teamspeak3*]
    env.teamspeak_query_user <query user login>
    env.teamspeak_query_user_password <query user password>
    env.teamspeak_host <Teamspeak3 host. Default: localhost>
    env.teamspeak_port <Teamspeak3 query port. Default: 10011>

to 

    /etc/munin/plugin-conf.d/munin-node

