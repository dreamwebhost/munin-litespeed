# munin-litespeed

Improved set of munin-plugins to monitor LiteSpeed.

Forked from https://github.com/burner1024/munin-litespeed

# Repository

- https://github.com/poralix/munin-litespeed

# Author

Modified/patched by Alex S Grebenschikov (www.poralix.com):

- litespeed_connections
- litespeed_requests
- litespeed_throughtput

Written by Alex S Grebenschikov (www.poralix.com):

- litespeed_hits
- litespeed_requests_post

# Installation

Simple if you have `git` installed:

```
git clone https://github.com/dreamwebhost/munin-litespeed.git
cp munin-litespeed/litespeed_* /etc/munin/plugins
chmod 755 /etc/munin/plugins/litespeed_*
service munin-node restart
```

# Configuration

Might need to add (for litespeed_requests_post plugin)

```
[litespeed_requests_post]
# env.log   /var/log/httpd/domains/*.log
user root
```

to `/etc/munin/plugin-conf.d/litespeed`
