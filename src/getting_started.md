# Getting started

## Prerequisites

Read the official documentation on how to set up your system at [tauri.app](https://tauri.app/v1/guides/)

## Choice of IDE

There are many IDE's to choose from, but for Rust development there are two that definitely stand out from the rest.

### IntelliJ

Any IntelliJ IDE is a valid option as long as it supports the Rust plugin. I recommend IntelliJ IDEA Ultimate simply because it allows you to work both with Rust and Javascript, so you can stay in one environment for both your frontend and backend coding.

The main reason I prefer IntelliJ over VSCode is because the code completion is far superior in IntelliJ.

### VSCode

VSCode is a valid option with the Rust extension, but be warned that the inferior code completion will make it harder to develop Rust.

## Recommended

You don't need these tools but they are recommended to have available.

### Cargo Commander

`cargo install cargo-commander`

When you're developing you're gonna want to save commands somehow. You can use `npm` and the scripts section of a package.json file, but that approach offers far fewer features and as a Rust programmer you prefer sticking with a Cargo/Rust approach.

Run `cargo cmd --help` for more information, and read its official documentation online.

### Tauri CLI

`cargo install tauri-cli`

You don't have to install the Cargo variant of the Tauri CLI, but as a Rust programmer you prefer sticking with Cargo tools. The npm variant and the cargo variant are built using the same source code, they perform the exact same task, it's just a matter of preference which one you pick.

Run `cargo tauri --help` for more information, and read its official documentation online.

### Npm/Yarn

`npm i -g yarn`

You don't NEED to have these installed technically, but frameworks that use WASM and allow you to completely stop using javascript are too early in their development to be used seriously. The ones that can be used seriously will have support for javascript packages one way or another. So regardless of how you decide to develop your frontend, you're definitely gonna want to use either `npm` or `yarn` to install packages. I prefer yarn over npm because it's much faster, but there have been moments when using yarn creates issues, so I tend to stard by using yarn and switch to npm if I encounter issues with it.

Run `npm --help` or `yarn --help` for more information, and read its official documentation online.
