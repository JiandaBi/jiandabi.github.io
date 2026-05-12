# Localhost 8080 Preview

This note records the local preview workflow that was used in WSL for this
Jekyll website.

## Quick Start

From WSL:

```bash
cd /home/bjd/mywebsite/_site
python3 -m http.server 8080 --bind 0.0.0.0
```

Then open this address in the Windows browser:

```text
http://localhost:8080
```

This serves the already-built static files in `_site`.

## Check That It Is Running

In another WSL terminal:

```bash
curl -I http://127.0.0.1:8080/
```

A working server should return a response like:

```text
HTTP/1.0 200 OK
```

To find the running process:

```bash
pgrep -af "python3 -m http.server 8080"
```

## Stop the Server

Use the PID returned by `pgrep`:

```bash
kill <PID>
```

Example:

```bash
kill 2774643
```

## Notes About Jekyll Rebuilds

The archived Ruby gems are under:

```text
/home/bjd/archive/gems
```

The archived gem environment can be exposed with:

```bash
export GEM_HOME=/home/bjd/archive/gems
export GEM_PATH=/home/bjd/archive/gems:/var/lib/gems/3.2.0:/usr/local/lib/ruby/gems/3.2.0:/usr/lib/ruby/gems/3.2.0:/usr/lib/x86_64-linux-gnu/ruby/gems/3.2.0:/usr/share/rubygems-integration/3.2.0:/usr/share/rubygems-integration/all:/usr/lib/x86_64-linux-gnu/rubygems-integration/3.2.0
export PATH=/home/bjd/archive/gems/bin:$PATH
```

At the time this note was written, `bundle exec jekyll --version` reached the
Jekyll environment but failed because `jekyll-minifier` needs a JavaScript
runtime and `node` was not available on PATH:

```text
Could not find a JavaScript runtime
```

So the reliable local preview path is currently the static `_site` server above.

## What This Does Not Do

This command does not rebuild the Jekyll site. If source files in `_pages`,
`_posts`, `_layouts`, `_includes`, assets, or `_config.yml` change, regenerate
`_site` with Jekyll first, then restart or refresh the static preview.
