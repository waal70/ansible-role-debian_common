Common
=========

This is the role that sets some defaults. You might say, a bootstrap role.

The role will check basic requirements. It will then determine the correct
course of action (mainly, "proper" Debian or Raspberry Pi debian)

This role should be safe to run on all machines, always.

It will perform the following:

* additional-firmware: perform the Thinkpad display driver fix. Install additional (vendor) firmware. Skips members of "proxmox_servers" group
* color-shell: set default colors for interactive shell
* custom-fact: deploy a small file that will retrieve some additional facts into ansible_facts
* edit-journald: configure journaling options. Vacuums the journal.
* motd: set a nice, colourful welcome message when logging in via interactive shell
* prereq-packages: installs (Python) packages and updates apt cache
* set-hostname: sets the hostname according to the configured value from ansible inventory
* set-locale: sets the default locale
* ssh-config: sets configuration for sshd, e.g. only allow login via certificates, disable root-login
* sudoers: makes sure ansible_user and interactive_user are in the sudoers
* tmp-nonexec: for hardening purposes, makes the /tmp folder non-executable
* unpriv-user: makes sure interactive_user is there and sets the ssh-keys for that user (Yubikey)

Requirements
------------

It requires a Debian instance, set-up by the preseed.
It will also accept a default Raspbian OS.
It also presumes a live sudo package.
Make sure at least the SSH-key for user ansible is set.

If you have proxmox-ve servers, for which Dell firmware should NOT be installed,
be sure to have them in a group called 'proxmox_servers'

Role Variables
--------------

None

License
-------

[GPLv3](https://www.gnu.org/licenses/gpl-3.0.html#license-text)

Author Information
------------------

Unless otherwise noted, this entire repository is (c) 2024 by André (waal70). [See github profile](https://github.com/waal70)

Please contact me if you need a commercial license for any of these files
