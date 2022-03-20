# SE_NGINX

A SELinux module for NGINX to write/delete files. 

## Before

Check your machine by

```shell
    getenforce
```

If you get nothing or "Permissive", it means your kernel don't installed SELinux or has been disabled.

## Installation

- Login as `root`, and clone the repository, then type:

```shell
    checkmodule -M -m -o se_nginx.mod se_nginx.te
    semodule_package -o se_nginx.pp -m se_nginx.mod
    semodule -i se_nginx.pp
```

- Check your NGINX can write and delete files to web directory on the SELinux machine which enabled

- If your NGINX still could not access any files, login as `root` and go to your web directory, type:

```shell
    chcon -R -t httpd_sys_content_t *
```

## LICENSE

[MIT License](LICENSE)

> Enjoy to use ;)
