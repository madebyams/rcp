# rcp

A simple CLI tool for sending files over a local network. Built in Rust.

> **Warning:** rcp has no encryption or authentication. Only use it on trusted local networks.

## Usage

```
rcp <local-file> <remote-filename>@<remote-address>[:<port>]
```

- `<local-file>` — path to the file you want to send
- `<remote-filename>` — filename to save as on the remote device
- `<remote-address>` — IP address or hostname of the remote device
- `<port>` — optional; defaults to `3000`

**Examples:**

```sh
# Send a file to a remote device on the default port
rcp photo.jpg photo.jpg@192.168.1.42

# Send to a specific port
rcp photo.jpg photo.jpg@192.168.1.42:4000
```

Files are compressed before transfer using zlib deflate.

## Building

Requires Rust and `libgtk-3-dev`:

```sh
# Debian/Ubuntu
sudo apt install libgtk-3-dev

cargo build --release
```

The binary will be at `target/release/rcp`.

## Contributing

PRs and issues are welcome.
