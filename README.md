# 3DS-SSL-Patch
This is a patch for the 3DS SSL module to disable Root CA Verification.

To use:

1. Download the `code.ips` file in the repository, and copy to `sdcard:/luma/titles/0004013000002F02/code.ips`.
2. Enable Game Patching under Luma3DS's configuration.

Compiling using the 0004013000002F02 title is also possible, by running `make` with the code.bin in this directory.

You may also need to send [ClCertA](https://github.com/SciresM/3DS-SSL-Patch/blob/master/ClCertA.p12?raw=true) as a client certificate. Unclear on that. A copy is included as a .p12 resource, with the password `3ds`.

~~**NOTE**: As of May 01, 2017, Luma3DS [doesn't actually support patching system modules](https://github.com/AuroraWright/Luma3DS/blob/master/injector/source/patcher.c#L853). You'll need to comment out the check on that line (`if(CONFIG(PATCHGAMES))` will do fine), and rebuild luma manually to use.~~ This doesn't seem to be the case anymore (but unknown when this change occurred)

I consider this to be a feature, not a bug, because having this installed will make it so that anyone can steal your 3ds's private information over the network because it makes all of your SSL requests insecure.

That said, it's very useful for MitM debugging of how the 3DS communicates with its servers.
