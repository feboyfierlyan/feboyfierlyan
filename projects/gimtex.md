# gimtex

A Rust command-line tool for turning selected source files into context for LLM workflows.

[Source & installation](https://github.com/feboyfierlyan/gimtex) · [Back to my profile](../README.md)

![Recorded gimtex CLI output](../assets/gimtex.svg)

## One small, reproducible workflow

Create a directory with these two files:

```rust
// src/config.rs
pub const APP_NAME: &str = "little-tool";
pub const VERSION: &str = "0.1.0";
```

```rust
// src/main.rs
fn main() {
    println!("Build something thoughtful.");
}
```

Run:

```sh
gimtex src/ -i '*.rs' -o context.md
```

The result is a file tree followed by each selected source file. The preview records a real run of version 2.6.0 on this fixture. Its payload was 87 tokens and 336 characters; these values describe this example only. Omit the filename comments when creating the two source files to reproduce the fixture exactly.

## What the tool handles

- Directory traversal and file-size limits.
- Glob filters, interactive file selection, and Git-diff extraction.
- A source tree, per-file token counts, and Markdown or XML output.
- Output to a file or the clipboard.
- Pattern-based redaction of some common secret formats. Review the output before sharing it; matching patterns cannot guarantee the absence of secrets.

The current `gimtex.toml` ignore list is parsed and logged but is not applied by the scanner. See the repository's current implementation and README for details.
