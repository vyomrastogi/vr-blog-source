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

---

### How to check for open ports in a unix machine

- `sudo` `netstat -tunlp`
  - `-t` - Show TCP ports.
  - `-u` - Show UDP ports.
  - `-n` - Show numerical addresses instead of resolving hosts.
  - `-l` - Show only listening ports.
  - `-p` - Show the PID and name of the listener’s process. This information is shown only if you run the command as root or sudo user.
- `netstat -tnlp | grep :22` - to filter for particular ports

---

### How to switch java versions easily

Nice discussion here : [so-link](https://stackoverflow.com/questions/21964709/how-to-set-or-change-the-default-java-jdk-version-on-macos)

_excerpt_

```shell
alias java17="export JAVA_HOME=`/usr/libexec/java_home -v 17`; java -version"
alias java11="export JAVA_HOME=`/usr/libexec/java_home -v 11`; java -version"
alias java8="export JAVA_HOME=`/usr/libexec/java_home -v 1.8`; java -version"
```
