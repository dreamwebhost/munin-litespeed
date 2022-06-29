# munin-litespeed

Improved set of munin-plugins to monitor LiteSpeed.


# Installation

```
git clone https://github.com/dreamwebhost/munin-litespeed.git
cp munin-litespeed/litespeed_* /etc/munin/plugins
chmod 755 /etc/munin/plugins/litespeed_*
service munin-node restart
```

# Configuration

Might need to configure logs path (for litespeed_requests_post plugin)

```
[litespeed_requests_post]
# env.log   /var/log/httpd/domains/*.log
user root
```

to `/etc/munin/plugin-conf.d/litespeed`
