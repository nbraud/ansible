nbraud.dev-debian
=================

This role sets up a Debian development environment, including
`sbuild`, `apt-cacher-ng`, and various QA tools.


Requirements
------------

Ansible 2.x is required.

- Debian and Ubuntu systems are supported (though Ubuntu is untested).
- The current incarnation of the role assumes the storage is a ZFS pool.


Role Variables
--------------

### Path hierarchy

- `debian__path`: Location for the build hierarchy; defaults to `/opt/deb`.
- `debian__overlay_path`: The location for schroot overlays, configured to be a
                          `tmpfs`; default: `/var/lib/schroot/union/overlay`.

### Build environment configuration

- `debian__extra_pkgs`: Additional packages installed in all `schroot` envs
                        created by this role; defaults to `[lintian]`.

- `debian__schroots`: List of `schroots` envs configured, with configurable attibutes:
  - `suite`: The Debian suite present in the environment (default: `sid`).
  - `name`: The name of the enviroment (defaults to the `suite` setting`).
  - `extra_pkgs`: List of additional packages to install (default: `[]`).


### ZFS

- `debian__zfs`: Whether ZFS integration is enabled; defaults to `no`.
- `debian__zpool_name`: Name of the ZFS pool, defaults to `dev`.
- `debian__zfs_dataset`: ZFS dataset under which to create Debian-related things,
                         defaults to `ansible_hostname`.


Example Playbook
----------------

This is a very basic example showing how to invoke the role:

    - hosts: all
      roles:
         - role: nbraud.dev-debian


License
-------

ISC
