# Minigrep

A simple command-line text search utility written in Rust. Search for patterns in files with support for case-sensitive and case-insensitive matching.

## Features

- **Case-sensitive search**: Find exact matches of your query
- **Case-insensitive search**: Find matches regardless of letter casing
- **Simple CLI**: Easy-to-use command-line interface
- **File reading**: Efficiently reads and searches through file contents

## Building

Make sure you have [Rust](https://www.rust-lang.org/) installed, then:

```bash
cargo build --release
```

The compiled binary will be available at `target/release/minigrep`.

## Usage

### Basic search (case-sensitive)

```bash
cargo run -- <query> <file>
```

Example:
```bash
cargo run -- "safe" poem.txt
```

### Case-insensitive search

Set the `IGNORE_CASE` environment variable to perform case-insensitive search:

```bash
IGNORE_CASE=1 cargo run -- <query> <file>
```

Example:
```bash
IGNORE_CASE=1 cargo run -- "rust" poem.txt
```

## Project Structure

```
src/
├── main.rs    - Entry point, CLI argument parsing, and file I/O
└── lib.rs     - Core search functions and tests
```

## Testing

Run the test suite:

```bash
cargo test
```

The project includes tests for:
- Case-sensitive search functionality
- Case-insensitive search functionality
- Correct filtering of matching lines

## Example

Given a file `poem.txt` with content:
```
Rust:
safe, fast, productive.
Pick three.
```

Running:
```bash
cargo run -- "safe" poem.txt
```

Will output:
```
safe, fast, productive.
```

## License

MIT
