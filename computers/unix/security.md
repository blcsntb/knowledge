# security
Sec is important, but hard. How do you keep your stuff in the clear?

## Pass
Pass is the unix password manager. Even though files are not stored as a binary
blob (ergo service names are retrievable), it's pretty much the best thing out
there. It's built on gpg and other unix tools, providing a neat interface for
local passwords. Use it.

## Hardware pgp management
The yubikey NEO is a hardware device to store your pgp keys. Unless it's
physically retrieved it cannot be read. Combine it with pass for maximum
security.

- [yubikey-neo-and-better-password-manager-pass](https://drupalwatchdog.com/blog/2015/6/yubikey-neo-and-better-password-manager-pass)
- [yubikey hardware](https://www.yubico.com/products/yubikey-hardware/yubikey-2/)

## Linux Security Modules
Linux security modules are part patches that live on the kernel, and part
userspace packages that interact with the kernel hooks to manage settings.

Linux Security Modules hooks were added in
[2001](https://en.wikipedia.org/wiki/Linux_Security_Modules).

### Apparmor
Define what system resources individual applications can access and with what
privileges. Static analysis and learning tools are included which make it
easier to manage.

__files__
- `/etc/apparmor.d/*`

- [apparmor-wiki/quick-profile-language](http://wiki.apparmor.net/index.php/QuickProfileLanguage)

### SELinux
Security Enhanced Linux. Provide more extensive permissions for files than
provided by the default linux distro (e.g. copy-only). Special patches must be
applied to GNU coreutils / busybox to detect the extended permissions.

## Mandatory Access Control (MAC)
- [wikipedia/mac](https://en.wikipedia.org/wiki/Mandatory_access_control)

## Basic security infrastructure
- [security guide](http://blog.mailgun.com/security-guide-basic-infrastructure-security/)
- [first 10 mins on a server](http://www.codelitt.com/blog/my-first-10-minutes-on-a-server-primer-for-securing-ubuntu/)
- [pen test cheat sheet](https://highon.coffee/blog/penetration-testing-tools-cheat-sheet/)

## Password testing
To test password strength, use `john(1)` aka [John the
Ripper](http://www.openwall.com/john/).

## Social engineering
A commonly used tool is the social engineering toolkit (SET) - allows setting
up fake wifi endpoints and more. Running this on yourself allows you to figure
out weak points in your own sec setup.

## Bluetooth
[btscanner](http://manpages.ubuntu.com/manpages/xenial/en/man1/btscanner.1.html)
and
[bluesniff](https://www.usenix.org/legacy/event/woot07/tech/full_papers/spill/spill.pdf)
are tools used to find bluetooth devices. Caution should be advised using
bluetooth devices as they could potentially get MITM or similar.

## Meterpreter
Ho-ly-shit this thing is only made for hacking other people. Real interesting
to play with to figure out how others would exploit your system / where the
limitations of the tool lie but... yeah. fuck.
