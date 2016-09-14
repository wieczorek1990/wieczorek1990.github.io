---
published: true
title: Checking file encoding
layout: post
tags: [encoding, uchardet, files]
---
# Example

Tired of checking file encodings?

~~~
cd $directory
for file in *; echo "$file — "(uchardet $file); end
~~~

# Packages
`uchardet`