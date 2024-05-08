## Socket Activation for Caddy (WIP)

Useful in deployments where sockets are passed by systemd.

### Usage

#### Caddy Configuration

```Caddyfile
https:// {
    bind socket-activation/https
    respond "ok"
}
```

Using socket activation requires every site block to have explicit **bind**, it can be used in a snippet to avoid repetition.

### Usage

#### Commandline

```bash
systemd-socket-activate -l 443 --fdname=http3 /path/to/caddy run
```

### Credits

FD to sockets mapping comes from [go-systemd](https://github.com/coreos/go-systemd/).