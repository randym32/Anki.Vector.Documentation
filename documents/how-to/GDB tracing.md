# How to trace calls using GDB

Vector's command line tools do not include a ptrace (as far as I can see).
This can be emulated with GDB.  Here is an example tracing a write() call.

1. Start gdb and attach to the process of interest.
1. Add the following scripted breakpoints:

```bash
    break write
    command
    silent
    printf "%d bytes\n", $r2
    x/80c $r1
    continue
    end
```

```bash
    set pagination off
```
