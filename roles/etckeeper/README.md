nbraud.etckeeper
================

This sets up `etckeeper`, along with some `sudo` and `zsh`
integration.


Requirements
------------

Ansible 2.x is required.

- Debian and Ubuntu systems are supported (though Ubuntu is untested).
- FreeBSD is supported starting with release 9.1, assuming pkgng is set up.


Role Variables
--------------

- `etckeeper__group`: Group that can passwordlessly query the
                      `etckeeper` state.

Example Playbook
----------------

This is a very basic example showing how to invoke the role:

    - hosts: all
      roles:
         - role: nbraud.etckeeper


License
-------

ISC
