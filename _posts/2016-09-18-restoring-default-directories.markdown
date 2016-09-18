---
published: true
title: Restoring default directories
layout: post
---
If you are using GNOME or similar desktop environment you might want sometimes delete default directories if you do not use them. Later on you figure out it would be cool to have them back, but when you create a new directory it does not have the good looking icon on it.

You can fix it with the below two commands which will regenerate the default directories.

~~~
rm ~/.config/user-dirs.dirs
xdg-user-dirs-update
~~~
