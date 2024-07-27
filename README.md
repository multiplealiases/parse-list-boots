# parse-list-boots

Parses the output of `journalctl --list-boots` and either provides uptime statistics:

```console
$ ./parse-list-boots
Uptime statistics from 29 boots

Minimum: 2 minutes and 8 seconds
Average: 3 hours 39 minutes and 15 seconds
Maximum: 1 days 3 hours 53 minutes and 4 seconds

Q1     : 47 minutes and 40 seconds
Median : 1 hours 57 minutes and 43 seconds
Q3     : 3 hours 20 minutes and 28 seconds
```

or prints raw uptimes with the `-r`/`--raw` option:

```console
$ ./parse-list-boots -r
2798
898
6828
755
128
(...and so on...)
```

## System Requirements

This script has a hard dependency on `systemd` as an init system,
though if different init systems have similarly trivial ways to find
uptimes across the lifetime of a system, let me know.

You will also need `jq` and `bc`.
