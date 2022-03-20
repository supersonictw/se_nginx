# SE_NGINX

A SELinux module for NGINX to write/delete files. 

## Before

Check your machine by

```shell
    getenforce
```

If you got "Permissive" or nothing, it means your SELinux has been disabled or uninstalled.

## Installation

If SELinux has been install on your machine, follow these step to unblock the limit to access files in web directory for NGINX.

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
