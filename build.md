# Build PMC from Source

To build PMC and automatically install it to your `~/.cargo/bin` directory, follow these instructions.

## Recommended: Background Build and Install

Since building can take several minutes on some systems, it is recommended to run it in the background:

```bash
# Navigate to the source directory
cd /home/maple/.picoclaw/workspace/sources/pmc

# Run cargo install in the background
nohup cargo install --path . > build.log 2>&1 &
```

You can check the progress by tailing the log:
```bash
tail -f build.log
```

## Standard Build and Install

If you prefer to wait for it to finish in your current terminal:

```bash
cargo install --path .
```

## What this does:
1.  **Compiles** the PMC source code in release mode.
2.  **Copies** the resulting binary to `/home/maple/.cargo/bin/pmc`.
3.  **Updates** your current PMC installation.

*Note: After installation, you should restart the PMC daemon to apply any changes:*
```bash
pmc daemon restart
```
