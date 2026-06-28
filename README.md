# minigrep

A small command-line search tool written in Rust, based on the project from
[The Rust Programming Language](https://doc.rust-lang.org/book/ch12-00-an-io-project.html)
book. It searches a file for lines containing a given string and prints the
matches.

## Usage

```bash
cargo run -- <query> <file_path>
```

For example, to search `poem.txt` for the word `body`:

```bash
cargo run -- body poem.txt
```

### Case-insensitive search

Set the `IGNORE_CASE` environment variable to perform a case-insensitive
search:

```bash
IGNORE_CASE=1 cargo run -- body poem.txt
```

## Building

Build a release binary with:

```bash
cargo build --release
```

The resulting executable can then be run directly:

```bash
./target/release/minigrep body poem.txt
```

## Testing

Run the unit tests with:

```bash
cargo test
```

## Project structure

- `src/main.rs` — argument parsing, configuration, and program entry point.
- `src/lib.rs` — the `search` and `search_case_insensitive` functions plus tests.
- `poem.txt` — sample text file to search against.
