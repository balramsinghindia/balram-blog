---
title: "SSL — Your connection to this site is not secure | AWS"
description: "SSL — Your connection to this site is not secure. Problem: I created few certificates for my website and one of them got active and i am not sure which one is active and how to delete it."
date: "2018-10-23T12:36:28.429Z"
categories: 
  - Ssl
  - AWS
  - Aws Ec2
  - DevOps

published: true
canonical_link: https://medium.com/@reactjavascript/ssl-your-connection-to-this-site-is-not-secure-34d443cc7f63
redirect_from:
  - /ssl-your-connection-to-this-site-is-not-secure-34d443cc7f63
---

**Problem:** I created few certificates for my website and one of them got active and i am not sure which one is active and how to delete it.

![](./asset-1.png)

**Solution:** Go to ssl.conf in below location and update path of new certificate

location of SSL files are in file

etc/httpd/conf.d

cat ssl.conf | grep -v ‘#’

![](./asset-2.png)
