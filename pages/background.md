---
layout: page
title: Background
---

Modern software applications tend to frequently process user private information such as usernames, passwords, credit records, encryption keys and health records. In most cases, <strong>only designated recipients should be allowed to access this secret data</strong>.

The operating system’s duty is to enforce security policies in order to eliminate unintentional leakage of those secrets to other users and applications. For example, the operating system can prevent unauthorized users or applications from accessing other users’ files or other applications’ memory space. The operating system can also restrict unprivileged users from accessing privileged regions such as the OS kernel. At the same time, applications also apply extra protection mechanisms such as data encryption to protect themselves from malicious parties even if the operating system itself is compromised.

However, there still persists a significant vulnerability in most of the computer systems. Even though there are numerous protection mechanisms one can apply to enhance security, there is virtually <strong>no strategy to defense a malicious party with administrative privileges</strong>. Such parties have unrestricted access to all system resources and all the running applications. Sophisticated malicious softwares can bypass protection schemes by extracting encryptions keys or even the secret data itself direct from the memory.

In order to defense such attacks and offer users higher level of protection of their secret data, Intel designed SGX(Software Guard Extension). In short, Intel SGX offers <strong>an extra set of CPU instructions to create enclaves</strong>, areas that are protected by hardware and ensure confidentiality and integrity even in front of privileged operating systems.
