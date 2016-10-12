---
published: true
title: Debugging Django code
layout: post
tags: [django, python, shell, debugging]
---
Ever tried debugging Django code in the CLI offered by `manage.py` `shell` or `shell_plus`?

It gets nasty when you need to write more than few lines of code to run something.

Here's what you can do instead:

~~~python
import os

import django


os.environ['DJANGO_SETTINGS_MODULE'] = 'project.settings'
django.setup()


def main():
    print 'Hello world!'


if __name__ == '__main__':
    main()
~~~