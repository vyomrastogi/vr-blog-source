---
title: "Important Links"
draft: false
menuTitle: "Important Links"
weight: 6
---

### SSLHandshakeException

```java
Exception: javax.net.ssl.SSLHandshakeException: sun.security.validator.ValidatorException: PKIX path building failed: 
    sun.security.provider.certpath.SunCertPathBuilderException: unable to find valid certification path to requested target

```
__Reason__ : jvm might need required certificates

__Possible Solution__ : [SO-Solution](https://stackoverflow.com/questions/21076179/pkix-path-building-failed-and-unable-to-find-valid-certification-path-to-requ)


### How to check for open ports in a unix machine

- `sudo` `netstat -tunlp`
  - `-t` - Show TCP ports.
  - `-u` - Show UDP ports.
  - `-n` - Show numerical addresses instead of resolving hosts.
  - `-l` - Show only listening ports.
  - `-p` - Show the PID and name of the listener’s process. This information is shown only if you run the command as root or sudo user.
- `netstat -tnlp | grep :22` - to filter for particular ports

