# Busybox HTTPD SH Server

A simple HTML templating SH solution that runs with just `httpd` and `sh` from `busybox`.

*(Note: Alpine Linux now splits Busybox into multiple packages: `apk add busybox-extras`)*

## Quickstart

Run the command:

```sh
busybox httpd -vv -fp 8080
```

And then open `http://localhost:8080` in your browser.

### FreeBSD

The demo syntax used in the interpreter script is not compatible with FreeBSD's `sh`.
The following patch makes it use the default Busybox `ash` applet installed via `pkg install busybox`:

```diff
diff --git a/interpreter.server_core_internal b/interpreter.server_core_internal
index 097f55f..604fe7f 100755
--- a/interpreter.server_core_internal
+++ b/interpreter.server_core_internal
@@ -1,4 +1,4 @@
-#!/bin/sh
+#!/usr/local/bin/busybox ash

 server_core_internal_file="${1:-index.html}"
```
