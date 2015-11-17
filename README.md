# proxy-gen

Tiny script to generate an nginx-based proxy with basic auth.

## Why is this useful?


I'm developing on a remote machine all the time, but I want to protect some
of the publicly accesible things and remain safe by locking it down as much
as possible.


## Dependencies

- Ruby
- nginx
- apache2-utils to generate valid htpasswd file



## Setup

1. Generate password file with:
  - `htpasswd -c ./mypass <username>`

2. Create your config file, you can use `proxy.yml.example` as a template

3. Run `./gen proxy.yml.example` - it will generate `proxy.conf`

4. Copy `proxy.conf` to `/etc/nginx/sites-available` and symlink it to `/etc/ngxin/sites-enables`

5. Open any ports listed in `gen`'s output using `iptables` of `ufw`
6. Reload `nginx`
7. Done!


## Problems?

Check nginx error log

---

Licensed under  GPL




