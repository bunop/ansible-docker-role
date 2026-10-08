ansible-docker-role
===================

Install Docker CE, the buildx and compose plugins from the official Docker
repository (`deb822` source with a `signed-by` key, no `apt-key`), and a
`docker-compose` wrapper calling `docker compose`.

Role Variables
--------------

- `docker_packages`: packages installed from the Docker repository
- `docker_compose_path`: path of the `docker-compose` wrapper
- `docker_daemon_options`: content of `/etc/docker/daemon.json`. By default
  published ports bind on `127.0.0.1` (docker bypasses ufw) and the
  `json-file` logs are rotated

Example Playbook
----------------

    - hosts: servers
      roles:
         - role: docker
