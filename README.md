## MacBook Pro 2017 Touchbar Linux kernel driver for Debian Trixie (w/ Kernel 6.12).

Introduction
------------

None of the MacBook Pro touchpad drivers worked for me on Debian Trixie (see https://github.com/Dunedan/mbp-2016-linux/issues/210).

This is a hacked version of https://github.com/t2linux/apple-ib-drv/.

- The first commit [https://github.com/schaecsn/apple-touchbar/commit/6c4af9d0883eec3247fa37e0a3456b04b2cf1aa3] removed the ibridge driver.
- The second commit [https://github.com/schaecsn/apple-touchbar/commit/f4f008f49a2ddb03b71981208ad985e3bd6df0a0] modifies the touchpad driver to a) shortcut the ibridge driver and b) hack around probe failures.

Alpha version - trust this and die.

Once Debian moves to a newer kernel with the release following Trixie, https://github.com/t2linux/apple-ib-drv/ hopefully works, again.


DKMS Setup
-----------

```
apt install dkms linux-headers-amd64
git clone https://github.com/schaecsn/apple-touchbar /usr/src/apple-touchbar-0.1
cd /usr/src/apple-touchbar-0.1
dkms install -m apple-touchpad -v 0.1
```
