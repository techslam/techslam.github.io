---
title: Set default Python version to Python3
date: 2019-10-13 21:00:00 +0100
categories: [Ubuntu, Python]
tags: [version]
seo:
  date_modified: 2019-10-13 21:47:51 +0100
---

A lot of us out there face issues while trying to point latest Python version as default. If you are facing issues while trying to install latest Python3 in your Ubuntu PC , but every attempt to change the default python version is in vain ?

I had to try a number of trial an error options before finally finding a simple solution for this.

Follow below simple steps and this should get your linux machine python installation default to Python3.

Assuming your current version is Python2, say Python 2.7 . And you have already performed Python3 installation, say Python 3.7

Add Python2.7 & Python 3.7 to `update-alternatives`

```shell
sudo update-alternatives --install /usr/bin/python2 python2 /usr/bin/python2.7 1
sudo update-alternatives --install /usr/bin/python3 python3 /usr/bin/python3.7 2
```

Update Python3 to point to Python 3.7

```shell
sudo update-alternatives --config python3
```
Enter 2 for Python 3.7

Test the version of python

```shell
python --version
```

Did this post help you with your issue ? Please leave your comments below.
