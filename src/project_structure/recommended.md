# Recommended

This is a highly opinionated view on what a "good" project structure is, so take the word "recommended" with a grain of salt. It's not some kind of standard best practise, it's just how I personally structure all of my projects and it makes for a really nice, logical layout.

You can see an example project using this structure at our Github repository: [https://github.com/how-do-you/banan](https://github.com/how-do-you/banan)

Here's an example of what it might look like for an organization with the domain name "example.rs":

- `.github` : Github configs
- `crates/` : All your projects where each project is added as a git submodule so they all have their own repository. See below for the structure of each of these crates
  - `rs-example` : Organization wide crate, named "example"
  - `rs-example-app` : The frontend of an application
  - `rs-example-app-tauri` : The Tauri backend for the frontend app
  - `rs-example-rest` : An actix-web REST API
  - `rs-example-api` : An interface to your REST API
- `Cargo.toml` : Virtual workspace
- `Commands.toml` : (Optional) Cargo Commander config file
- `README.md` : You know what this is
- `.gitpod.Dockerfile` : (Optional) Docker config for Gitpod
- `.gitpod.yml` : (Optional) Gitpod config

Each crate in the `crates/` directory has the following base structure, no matter what you're developing:

- `.github` : Crate specific Github configs
- `book/` : Mdbook documentation for your project
- `examples/` : Examples
- `src/` : Source code
  - `lib.rs` : If it's a library or a frontend project
  - `main.rs` : If it's a binary project
- `build.rs` : Build script
- `README.md`
- `Cargo.toml`
