# spandock.server

An Ansible role that installs a [SpanDock](https://www.spandock.com) server (a hub, or a satellite that joins one) as a systemd service, with the `spandock` command for its CLI.

```yaml
- hosts: spandock
  become: true
  roles:
    - role: spandock.server
      # spandock_join_code: "…"           # add a satellite (from the hub: Settings → Scaling → Add server)
      # spandock_public_listen: 0.0.0.0:443 # public endpoint with automatic HTTPS
      # spandock_public_name: edge
      # spandock_public_domain: example.com
```

Needs Ubuntu 24.04, Debian 13, RHEL 10 or newer (glibc 2.38+), with systemd. Variables and defaults are in `defaults/main.yml`. A new hub prints an activation link (`journalctl -u spandock -f`): approve it once on spandock.com. Full guide: https://www.spandock.com/docs/deploy

Generated from SpanDock's deploy kits (https://github.com/SpanDock/spandock-deploy); open issues there. Licensed under Apache-2.0.
