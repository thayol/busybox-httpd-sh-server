# Busybox HTTPD SH Server

A simple HTML templating SH solution that runs with just `httpd` and `sh` from `busybox`.

*(Note: Alpine Linux now splits Busybox into multiple packages: `apk add busybox-extras`)*

## Quickstart

Run the command:

```sh
busybox httpd -vv -fp 8080
```

And then open `http://localhost:8080` in your browser.
