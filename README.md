discv5-cli
============

[![Build Status]][Build Link] [![Doc Status]][Doc Link] [![Crates
Status]][Crates Link]

[Build Status]: https://github.com/AgeManning/discv5-cli/workflows/build/badge.svg?branch=master
[Build Link]: https://github.com/AgeManning/discv5-cli/actions
[Doc Status]: https://docs.rs/discv5-cli/badge.svg
[Doc Link]: https://docs.rs/discv5-cli
[Crates Status]: https://img.shields.io/crates/v/discv5-cli.svg
[Crates Link]: https://crates.io/crates/discv5-cli

[Documentation at docs.rs](https://docs.rs/discv5-cli)

## Overview

This is a simple CLI utility for creating and debugging discovery v5 servers.

## Install

This can be installed via cargo:

```bash
$ cargo install discv5-cli
```

## Usage

```
Sigma Prime <contact@sigmaprime.io>
Simple CLI tool for starting and debugging discv5 servers and packets. This currently runs a discv5 server which
regularly performs peer search queries

USAGE:
    discv5-cli [OPTIONS] [SUBCOMMAND]

FLAGS:
    -h, --help       Prints help information
    -V, --version    Prints version information

OPTIONS:
    -v, --log-level <level>    Specifies the listening address of the server. [default: info]  [possible values: trace,
                               debug, info, warn, error]

SUBCOMMANDS:
    help           Prints this message or the help of the given subcommand(s)
    packet         Performs various packet encoding/decoding functions
    request-enr    Requests the ENR of a multiaddr
    server         Runs a discv5 test server
```

## Example

```bash
$ ./discv5-cli server -l 127.0.0.1 -p 9001 -w -e -IS4QCs0BSKEvnX8om4rAAi7D2p2lwQ7LVpAeESY2ikm1b5dBOqJC7istWMVg06dy-I09C8NuZdodEFNxIiiolWwSWkBgmlkgnY0gmlwhH8AAAGJc2VjcDI1NmsxoQPKY0yuDUmstAHYpMa2_oxVtw0RW_QAdpzBQA8yWM0xOIN1ZHCCIyg 

2020-05-20 21:15:06,968 INFO  [discv5_cli::server] Node Id: 0x62e5..2ca7
2020-05-20 21:15:06,968 INFO  [discv5_cli::server] Base64 ENR: enr:-IS4QKzeZIMc6NtdIYGTQvo0Q2Aw0NicbQrW7zArKWU6iNebWMuBTjJnes8nBJ-wAua-W6XNatKBHrNhxFcaUSysVJwBgmlkgnY0gmlwhH8AAAGJc2VjcDI1NmsxoQIAN7xJ9ce7O7iw-dFrlOzj4sC1Y0Gvic5hb5Rxfs4Xt4N1ZHCCIyk
2020-05-20 21:15:06,968 INFO  [discv5_cli::server] ip: 127.0.0.1, udp port:9001
2020-05-20 21:15:06,969 INFO  [discv5_cli::server] Connecting to ENR. ip: Some(127.0.0.1), udp_port: Some(9000),  tcp_port: None
2020-05-20 21:15:06,971 INFO  [discv5_cli::server::query_server] Connected Peers: 0
2020-05-20 21:15:06,971 INFO  [discv5_cli::server::query_server] Searching for peers...
2020-05-20 21:15:10,973 INFO  [discv5_cli::server::query_server] Query Completed. No peers found.
```
