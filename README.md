# 3DS-SSL-Patch
This is a patch for the 3DS SSL module to disable Root CA Verification.

To use:

1. Download and decrypt the SSL module (0004001000002F02), and extract its code binary to the patch directory as "code.bin"
2. Run `make`.
3. Copy to `sdcard:/luma/titles/0004001000002F02/code.bin`.
4. Enable Game Patching under Luma3DS's configuration.

**NOTE**: As of May 01, 2017, Luma3DS [doesn't actually support patching system modules](https://github.com/AuroraWright/Luma3DS/blob/master/injector/source/patcher.c#L853). You'll need to comment out the check on that line (`if(CONFIG(PATCHGAMES))` will do fine), and rebuild luma manually to use.

I consider this to be a feature, not a bug, because having this installed will make it so that anyone can steal your 3ds's private information over the network because it makes all of your SSL requests insecure.

That said, it's very useful for MitM debugging of how the 3DS communicates with its servers.