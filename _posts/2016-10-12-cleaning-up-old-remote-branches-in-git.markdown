---
published: true
title: Cleaning up old remote branches in Git
layout: post
---
This time in fish.

~~~fish
git fetch origin --prune
git fetch --all
for branch in (git branch --remote | egrep -v 'develop|master|\*' | tr -d ' ' | sed 's/origin\///'); git push origin ":$branch"; end
~~~