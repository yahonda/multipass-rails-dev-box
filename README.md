# multipass-rails-dev-box

You can run rails-dev-box on M1 mac using Multipass.

# How to build "rails-dev-box"

1. Download [Multipass](https://multipass.run)
2. Clone this repository

```
% git clone https://github.com/yahonda/multipass-rails-dev-box.git
% cd multipass-rails-dev-box
```

3. Launch Multipass box

```shell
% multipass launch 24.04 --cpus 2 --disk 20G --memory 2G --name rails-dev-box --cloud-init ./cloud-init.yaml --timeout 600
```

4. Login to Multipass box

```shell
% multipass shell rails-dev-box
```

5. You can access the "rails-dev-box"

```shell
ubuntu@rails-dev-box:~$
```

# What's included

## Databases

- **MySQL**: A `rails` user is created with no password. Root also has an empty password so Rails-generated test applications can run `db:create` without additional configuration.
- **PostgreSQL**: A superuser `ubuntu` is created.

## Environment variables

The following environment variables are set in `~/.profile` so they are available in non-interactive login shells (e.g. `bash -l -c`):

| Variable | Value | Purpose |
|---|---|---|
| `MYSQL_SOCK` | `/var/run/mysqld/mysqld.sock` | MySQL Unix socket path for Trilogy and mysql2 adapters |
| `SE_MANAGER_PATH` | `/usr/local/bin/selenium-manager` | Overrides the bundled x86_64-only selenium-manager binary |

## Ruby

Ruby is managed via [mise](https://mise.jdx.dev/). The default Ruby version is installed automatically during provisioning.
