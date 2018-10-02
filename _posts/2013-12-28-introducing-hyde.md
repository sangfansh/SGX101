---
layout: post
title: Overview
excerpt_separator:  <!--more-->
---

Intel SGX (Software Guard Extension) is a new instruction set in Skylake Intel CPUs since autumn 2015. It provides a reverse sandbox that protects enclaves from: 

- OS or hypervisor
- BIOS, firmware, drivers
- System management module (Ring 2)
- Intel management engine (ME)
- Any remote attack
In short, SGX architecture is a hardware-enforced security mechanism that requires **Trusted Computing Base (TCB), Hardware Secrets, Remote Attestation, Sealed Storage and Memory Encryption**.

Here, **TCB** will be the CPU’s package boundary and software components related to SGX.

**Hardware Secrets** will be two 128-bit keys at production: Root Provisioning Key and Root Seal Key. Notice that RPK is known to Intel and RSK is not, therefore most of he derived key are based on RSK. We will discuss this later in the tutorial.

**Remote Attestation** is enforced for the client to prove to the service provider that an enclave is running a given software, inside a given CPU, with a given security level, for a given Individual Software Vender (ISV). This is required before the service provider decides to provide requested secrets.

**Sealed Storage** is required to save secret data to untrusted media. Data and code inside enclaves are not secrets. They are just logics that are required to process the secret and most of them are open sourced or can be reverse engineered. Therefore, secrets are provisioned later by the service provider and should be stored out of the enclave through sealing mechanism when necessary (e.g. for future usage).

In summary, Intel SGX offers the following protections from known hardware and software attacks:

- Enclave memory cannot be read or written from outside the enclave regardless of the current privilege level and CPU mode.
- Production enclaves cannot be debugged by software or hardware debuggers. 
- The enclave environment cannot be entered through classic function calls, jumps, register manipulation, or stack manipulation. The only way to call an enclave function is through a new instruction that performs several protection checks.
- Enclave memory is encrypted using industry-standard encryption algorithms with replay protection. Tapping the memory or connecting the DRAM modules to another system will yield only encrypted data.
- The memory encryption key randomly changes every power cycle. The key is stored within the CPU and is not accessible.
- Data isolated within enclaves can only be accessed by code that shares the enclave.

As a result, the attack surface can be largely reduced after applying Intel SGX:
![Attack Surface](/hydeout/assets/pics/overview1/png)