# ares

## Development

### Librashader

Since Librashader is built in Rust, a `cargo-sources.json` file is required to install the required dependencies. The `cargo-sources.json` file typically needs to be updated when ares bumps its Librashader version. This section will cover how to update that file. 

1. Identify the required Librashader version by looking at the `librashader` file, [https://github.com/ares-emulator/ares-deps/blob/main/deps.windows/librashader](https://github.com/ares-emulator/ares-deps/blob/main/deps.windows/librashader).
2. Download and extract the corresponding Librashader version to a folder of your choice:
    * https://api.github.com/repos/SnowflakePowered/librashader/tarball/librashader-v#.#.#
    * Replace the `#.#.#` with the version you located in Step 1.
3. Download the latest `flatpak-cargo-generator.py` file from https://github.com/flatpak/flatpak-builder-tools/blob/master/cargo/flatpak-cargo-generator.py and place the file in the root of the extracted Librashader folder.
4. Use the following command to convert the `Cargo.lock` file in the Librashader root folder to a `cargo-sources.json` file:
    * `python3 ./flatpak-cargo-generator.py ./Cargo.lock -o cargo-sources.json`
4. Once the `cargo-sources.json` file is created, replace the current `cargo-sources.json` file with the latest version.
