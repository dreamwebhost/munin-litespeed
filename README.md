# munin-litespeed

Improved set of munin-plugins to monitor LiteSpeed.

Forked from https://github.com/poralix/munin-litespeed


# Installation

```
git clone https://github.com/dreamwebhost/munin-litespeed.git

mkdir -p /usr/local/munin/lib/plugins
cp munin-litespeed/litespeed_* /usr/local/munin/lib/plugins/
chmod 755 /usr/local/munin/lib/plugins/litespeed_*

ln -s /usr/local/munin/lib/plugins/litespeed_hits /etc/munin/plugins/litespeed_hits
ln -s /usr/local/munin/lib/plugins/litespeed_requests /etc/munin/plugins/litespeed_requests
ln -s /usr/local/munin/lib/plugins/litespeed_connections  /etc/munin/plugins/litespeed_connections

# throughtput graph does not show real/correct throughtput because of how LSWS provide stats
ln -s /usr/local/munin/lib/plugins/litespeed_throughtput /etc/munin/plugins/litespeed_throughtput

# optional plugin to count POST request in access log file
ln -s /usr/local/munin/lib/plugins/litespeed_requests_post /etc/munin/plugins/litespeed_requests_post

```

# Configuration

Create file `/etc/munin/plugin-conf.d/litespeed` and add the folowing...

```
[litespeed_*]
user nobody
```

Might need to configure logs path (only for litespeed_requests_post plugin)

```
[litespeed_requests_post]
env.log   /var/log/httpd/domains/*.log
user nobody
```

# Restart
```
service munin-node restart
```
