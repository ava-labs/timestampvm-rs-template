# `timestampvm-rs-template`

`timestampvm-rs-template` is a [cargo generate](https://cargo-generate.github.io/cargo-generate/) template for [timestampvm-rs](https://github.com/ava-labs/timestampvm-rs), a minimal implementation of an Avalanche custom virtual machine (VM) in Rust, using the Avalanche [Rust SDK](https://github.com/ava-labs/avalanche-types-rs).

## Usage
First install `cargo generate`

```cargo install cargo-generate```

then to use this template run:

```cargo generate --git https://github.com/ava-labs/timestampvm-rs-template --name myproject```

## Dependencies

- Latest version of stable Rust.
- To build and test timestampvm you need [protoc](https://grpc.io/docs/protoc-installation/#install-pre-compiled-binaries-any-os) version >= 3.15.0.

## Build the plugin

```
# Use the build script
./scripts/build.release.sh

# or build using cargo

cargo build --release --bin {{project-name}}
```

## Run e2e tests
```
VM_PLUGIN_PATH=$(pwd)/target/release/{{project-name}} \
./scripts/tests.e2e.sh

# or, specify the custom avalanchego binary
VM_PLUGIN_PATH=$(pwd)/target/release/timestampvm \
./scripts/tests.e2e.sh ~/go/src/github.com/ava-labs/avalanchego/build/avalanchego

# (optional) set NETWORK_RUNNER_ENABLE_SHUTDOWN=1 in "tests.e2e.sh"
# to shut down the network afterwards
```

For more examples see the [timestampvm-rs](https://github.com/ava-labs/timestampvm-rs#examples) repo.
