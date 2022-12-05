# States

A state in Tauri is essentially a key-value pair storage for variables in Rust that persist for the duration of your app run. They make it possible to easily access variables across commands and threads.

```rust
#![cfg_attr(
all(not(debug_assertions), target_os = "windows"),
windows_subsystem = "windows"
)]

use tauri::{Manager, State};

struct MyInt(isize);
struct MyString(String);

#[tauri::command]
fn int_command(state: State<MyInt>) -> String {
    format!("The stateful int is: {}", state.0)
}

#[tauri::command]
fn string_command<'r>(state: State<'r, MyString>) {
    println!("state: {}", state.inner().0);
}

fn background_thread(app: AppHandle) {
    loop {
        let my_int: State<MyInt => app.state();
        println!("{}",my_int);
        std::thread::sleep(std::time::Duration::from_millis(1000));
    }
}

fn main() -> Result<(), ()> {
    tauri::Builder::default()
        .manage(MyInt(0))
        .manage(MyString("tauri".into()))
        .setup(|app| {
            let handle = app.handle();
            tauri::runtime::spawn(background_thread(handle));
            Ok(())
        })
        .run(tauri::generate_context!())
        .expect("error while running tauri application");
    Ok(())
}

```

## References

- [State](https://docs.rs/tauri/1.0.0/tauri/struct.State.html)
- [StateManager](https://docs.rs/tauri/1.0.0/tauri/struct.StateManager.html)
