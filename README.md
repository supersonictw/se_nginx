# SE_NGINX
A SELinux Module for Nginx to Write/Delete Files

## Before
Type

    getenforce

If you get nothing or "Permissive", quit there.
It means your Kernel do not or disable have SELinux.

## Installation
Login as ROOT user, and than clone the Repo and type:

    checkmodule -M -m -o se_nginx.mod se_nginx.te
    semodule_package -o se_nginx.pp -m se_nginx.mod
    semodule -i se_nginx.pp

## After
Check your Nginx can write and delete files to web directory on the SELinux Enabled Machine
### If your Nginx still could not access to view any files
Login as ROOT and go to your web directory, type:

    chcon -R -t httpd_sys_content_t *


## LICENSE
[MIT License](LICENSE)
> Enjoy to use ;)
