# ansible-role-nginx [![Build Status](https://travis-ci.org/hugomrdias/ansible-role-nginx.svg?branch=master)](https://travis-ci.org/hugomrdias/ansible-role-nginx)
> Role to install Thumbor in Debian/Ubuntu systems

This is for advanced users.

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
