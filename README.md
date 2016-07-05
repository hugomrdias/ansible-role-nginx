# ansible-role-nginx [![build status](https://gitlab.com/hugomrdias/ansible-role-nginx/badges/master/build.svg)](https://gitlab.com/hugomrdias/ansible-role-nginx/commits/master)
> Role to install Thumbor in Debian systems

This is for advanced users. This is only for Debian uses stretch sources to install nginx to enable http2 with ALPN support using openssh 1.0.2+

A base ssl conf is available at `/etc/nginx/conf.d/ssl/ssl.conf` to be included although to be used you need to generate `dhparam` first with `openssl dhparam -out /etc/nginx/conf.d/ssl/dhparam.pem 2048` or 4096.
After that you just need to add the following directives to each server and this should give you an A+ score in SSL Labs.

```
ssl_certificate /etc/nginx/conf.d/ssl/domain.chained.pem;
ssl_certificate_key /etc/nginx/conf.d/ssl/domain.key;
ssl_trusted_certificate /etc/nginx/conf.d/ssl/domain.chained.pem;
```

This role uses synchronize module so you need to enable sudo without password atleast for rsync
```
# file: /etc/sudoers
%sudo   ALL=(ALL:ALL) ALL, NOPASSWD: /usr/bin/rsync
```

## Requirements
None   

## Role Variables
Check `defaults/main.yml`

## Dependencies
None

## Example Playbook

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: servers
      roles:
         - { role: hugomrdias.nginx }

## Resources
### nginx, tcp tuning
https://www.linode.com/docs/websites/nginx/configure-nginx-for-optimized-performance   
https://tweaked.io/guide/nginx/   
http://www.revsys.com/12days/nginx-tuning/   
http://dak1n1.com/blog/12-nginx-performance-tuning/   
https://t37.net/nginx-optimization-understanding-sendfile-tcp_nodelay-and-tcp_nopush.html   
http://serverfault.com/questions/775298/debian-jessie-nginx-with-openssl-1-0-2-to-use-alpn-rather-than-npn   
https://wiki.debian.org/AptPreferences#Pinning   


## nginx
### installing custom nginx build with nchan
https://serversforhackers.com/compiling-third-party-modules-into-nginx   
https://github.com/slact/nchan/releases

```
# package to install after rebuild
nginx-common
libnginx-mod-http-geoip
libnginx-mod-http-image-filter
libnginx-mod-http-xslt-filter
libnginx-mod-mail
libnginx-mod-http-auth-pam
libnginx-mod-stream
nginx-full

```


## License
MIT © [Hugo Dias](http://hugodias.me)
