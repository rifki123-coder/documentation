# Using Mounts

Mounts is a feature that allows administrators to mount other directories from the host file-system into a Server's container.

## Wings Configuration

For security reasons it is not possible to mount directories on a node by default. Directories that should be mountable have to be specified explicitly in the Wings configuration.

In the Wings configuration file (`/etc/pterodactyl/config.yml`) the `allowed_mounts` field is used to list mountable directories. The listed directories and all their subdirectories can be mounted.

```yml
allowed_mounts:
- /example
```

You have to restart Wings to apply new changes to your Wings config.

## Panel Configuration

You have to configure mounts in admin Panel in order to use them with your servers. They consist of a source pad on the node and a target path where it will be mounted in the container.

::: tip Path in the container
Mounts can be mounted to or inside of `/home/container` or any subdirectory of it. You can cross-mount servers such as Server A's directory into Server B.
Keep in mind that the folder you want to mount into needs to exist for the mount to work.
:::

### Creating
