# Subgraph kernel configs

This is a repository of kernel configurations for Subgraph OS.

The aim of our kernel configuration is to provide support for commodity
desktop hardware while removing exotic, legacy and uncommon options that would 
be compiled in normally or available as modules. The upshot of this is also
that we can reduce the attack surface in the Subgraph OS kernel. So we're
also keeping track of what we have removed inside of this repository.

It is also worth noting that our kernel configurations include grsecurity 
options (and therefore require that the kernel is patched with the grsecurity
testing patch for each version).

Each kernel configuration is placed in a directory named after the upstream
version.

We started this reduction as of upstream kernel version 4.2.3 (using Debian the
Debian 4.2.x configuration as a starting point). This is an ongoing effort 
(we'll update this README with our progress).

## Removed options

Some of the areas we have removed so far include:

Networking Support:
- Plan 9 Resource Sharing Support
- The IPX protocol
- IrDA
- X.25/LAPB 
- Phonet protocols family
- B.A.T.M.A.N. Advanced Meshing Protocol
- Amateur Radio Support
- CANBUS
- IPv6 (not supported by Subgraph OS as it is not well-supported by Tor)

Device drivers:
- Parallel port support

## FAQ

1. Why not start with a minimal configuration and add only what is needed?

Good question. Part of this exercise is to compare what a normal Debian
kernel includes in relation to our reduced configuration. Another part of this
exercise is to run a fine-toothed comb over everything that typically ships
in desktop operating system kernels.

We also test these kernels so eliminating options from a working kernel to
see if anything breaks is a better approach for us.

