---
published: true
title: uWSGI maximum scoket connections
layout: post
---
Were you ever wondering why are you getting HTTP 502 responses from your uWSGI on high connection count?

Setting `net.core.somaxconn` might help.

Temporarily:

~~~
$ cat /proc/sys/net/core/somaxconn
# echo 4096 > /proc/sys/net/core/somaxconn
~~~

Temporarily with `sysctl`:

~~~
# sysctl -w net.core.somaxconn=1024
~~~

~~~
# echo 'net.core.somaxconn=1024' >> /etc/sysctl.conf
~~~

Reload kernel parameters after changes:

~~~
# sysctl -p
~~~

Change uWSGI settings for vassal:

~~~
cat /etc/uwsgi/vassals/vassal.ini
echo 'listen = 1024' >> /etc/uwsgi/vassals/vassal.ini
~~~

Restart uwsgi:

~~~
service uwsgi restart
~~~