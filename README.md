# Build pipeline

See the Makefile.


## Development Workflow

### Making Changes
1. Create a separate branch for each change.
2. Make a focused change and commit it with a clear message.
3. Open a pull request against `main`.
4. Request a peer review and address review feedback before merging.

### Build and Test

Run these commands from the repository root. The `src/` directory must contain at least one `.txt` file.

- `make check` — verifies that the source directory exists and contains `.txt` files.
- `make build` — converts each `src/*.txt` file to uppercase and writes the output to `out/`.
- `make test` — builds the files and checks that no lowercase characters remain in the generated outputs.
- `make ci` — runs `clean`, `check`, and `test` in sequence.
- `make clean` — removes the generated `out/` directory.

#### Expected successful output

For `make check`, expect a message like:

`CHECK PASSED: 2 source file(s) found`

The number depends on how many `.txt` files are present in `src/`.

For `make build`, expect messages like:

`BUILD src/example.txt -> out/example.txt`

For `make test`, expect:

`TEST PASSED`

For `make ci`, expect the successful check and test messages, along with any build messages for the source files.

If a required source directory or `.txt` file is missing, `make check` reports a `CHECK FAILED` message. If lowercase characters remain in generated outputs, `make test` reports `TEST FAILED`.
### Code Review
Reviewers should provide specific, actionable feedback. Authors should respond to review comments and make necessary updates before merging.
