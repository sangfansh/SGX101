---
layout: page
title: "Get Started"
---

Now let’s get started by prepare the environment for Intel SGX.

Before installing Intel SGX SDK, we have to first purchase an SGX-enabled Skylake CPU. Then SGX option has to be enabled in system BIOS. Finally, the Intel SGX SDK and Platform Software need to be downloaded. This tutorial will be focusing on Intel SGX on Linux using Ubuntu 16.04. SDK is available [here](https://github.com/intel/linux-sgx).

Please follow the instructions to get Intel SGX SDK and PSW ready.

The **Intel SGX Platform Service (PSW)** is required to run SGX enclaves. It contains drivers, services and Intel privileged enclaves for launch policy enforcement, EPID and remote attestation service and provisioning service.

The **Intel SGX SDK** is required to develop SGX enclaves and applications. It contains Intel custom libc and cryptographic libraries, each with 2 versions (debug & release). It also has tools such as `sgx_edger8r` to generate glue code (we will discuss this in the enclave tutorial) and `sgx_sign` to sign enclaves with development key.

After all the required libraries are installed, we can start developing applications with SGX in mind!