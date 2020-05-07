## Arch Linux

Bitwarden_rs is already packaged for Archlinux thanks to @mqus. There is an [AUR package](https://aur.archlinux.org/packages/bitwarden_rs) (optionally with the [vault web interface](https://aur.archlinux.org/packages/bitwarden_rs-vault/) ) available.

## Debian

A docker based toolchain can be used to build debian packages: https://github.com/greizgh/bitwarden_rs-debian
It bundles the server and the web vault.


## CentOS7 / RHEL7

A RPM Repository is packaged by @MrMEEE here: https://copr.fedorainfracloud.org/coprs/mrmeee/bitwarden_rs/ ... This also includes the webinterface in an additional package. 

Installation instructions: https://github.com/MrMEEE/bitwarden_rs_rpm/blob/master/README.md

Any issues with the RPMs can be reported here: https://github.com/MrMEEE/bitwarden_rs_rpm/issues

## Cloudron

[Cloudron](https://cloudron.io) is a platform that helps you run web apps on your server. 
Using Cloudron, you can easily install Bitwarden_rs on a custom domain from the [App Library](https://cloudron.io/store/com.github.bitwardenrs.html)
The app package comes bundled with the upstream web vault and does not need any further configuration after installation to get started. The Cloudron team keeps track of releases and provides automatic updates.

The package code and the issue tracker can be found at https://git.cloudron.io/cloudron/bitwardenrs-app
 