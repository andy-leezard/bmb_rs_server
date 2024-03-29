# A Personal webserver project designed to learn Rust

The project is tested on Debian Linux

# Requirements

- Docker (cause i'll dockerize it)

# Dependencies

- Surreal DB
- tungstenite (Websocket)
- jsonwebtoken (Auth)

# STEPS

1. Install Rust via RustUp.

```
$ curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh
```

2. Install Cargo Watch

```
$ cargo install cargo-watch
```

- Cargo Watch watches over your project's source for changes, and runs Cargo commands when they occur.

By default, it runs check. You can easily override this, though:

```
$ cargo watch [-x command]...
```
- A few examples:

```
# Run tests only
$ cargo watch -x test

# Run check then tests
$ cargo watch -x check -x test

# Run run with arguments
$ cargo watch -x 'run -- --some-arg'

# Run an arbitrary command
$ cargo watch -- echo Hello world

# Run with features passed to cargo
$ cargo watch --features "foo,bar"
```

3. Create a new project

```
$ cargo new your_project_name
```

4. Install Dependencies

Add the necessary dependencies for SurrealDB, WebSockets and authentication to your ```Cargo.toml``` file.

- will be installed in a folder named "target"

```
$ cargo check
```

This command will perform a quick check of the project's dependencies to see if there are any updates available.
If any updates are found, you will receive a message indicating the name and version of the outdated dependency.

If you want to update all of the outdated dependencies in your project, you can run the following command:

```
$ cargo update
```

This command will update all of the dependencies to the latest available version.
Be aware that updating dependencies can sometimes result in breaking changes,
so it's important to thoroughly test your project after updating dependencies.


4. Run

```
# For synchronous main fn
$ cargo run

# For asynchronous main fn
$ cargo watch -q -c -x "run -q"
```