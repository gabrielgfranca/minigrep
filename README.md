# Minigrep

A simple command-line text search tool written in Rust, inspired by the `grep` utility and built while following Chapter 12 of *The Rust Programming Language* book.

## Features

* Search for text inside files
* Case-sensitive search
* Case-insensitive search using the `IGNORE_CASE` environment variable
* Error handling for invalid input and file operations
* Output redirection support through standard shell operators

## Usage

```bash
cargo run -- <query> <file_path>
```

### Example

```bash
cargo run -- duct poem.txt
```

### Case-Insensitive Search

Linux/macOS:

```bash
IGNORE_CASE=1 cargo run -- duct poem.txt
```

Windows PowerShell:

```powershell
$env:IGNORE_CASE=1
cargo run -- duct poem.txt
```

## Example Output

```text
safe, fast, productive.
Duct tape.
```

## Saving Output to a File

You can redirect the program's output to a file using the shell redirection operator (`>`).

```bash
cargo run -- duct poem.txt > output.txt
```

After running the command, the search results will be written to `output.txt`.

### Example

Contents of `poem.txt`:

```text
Rust:
safe, fast, productive.
Pick three.
Duct tape.
```

Command:

```bash
cargo run -- duct poem.txt > output.txt
```

Contents of `output.txt`:

```text
safe, fast, productive.
Duct tape.
```

## Project Structure

```text
src/
├── main.rs      # Application entry point
└── lib.rs       # Search logic and configuration
```

## Built With

* Rust
* Cargo

## Learning Goals

This project was created to practice:

* Command-line argument parsing
* Error handling with `Result`
* File I/O
* Modules and crates
* Testing
* Environment variables
* Ownership and borrowing

## References

* *The Rust Programming Language* — Chapter 12: *An I/O Project: Building a Command Line Program*

## License

This project was created for educational purposes while learning Rust.
