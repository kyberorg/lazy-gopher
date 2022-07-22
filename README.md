# Lazy Gopher
Go program, that does literally nothing, but runs forever (until stopped).

## Why?
1. Just for fun
2. Maybe used as docker entrypoint

## Usage
### Minimal working example
```shell
lazy-gopher
```

### As docker entrypoint
```dockerfile
CMD ["/lazy-gopher"]
```

### SystemD daemon example
```
[Unit]
Description=Lazy Gopher

[Service]
Type=simple
Restart=always
RestartSec=5s
ExecStart=/usr/local/bin/lazy-gopher

[Install]
WantedBy=multi-user.target
```

## Build
### With make
```shell
make binary
```

### Without make
```shell
 CGO_ENABLED=0 go build github.com/kyberorg/lazy-gopher/cmd/lazy-gopher
```

## Compress binary
**This requires `upx`**
### With make
```shell
make compress-binary
```

### Without make
```shell
upx --brute bin/lazy-gopher
```