## Memory managment


### Rust - copy vs move

```rs[2]
fn main() {
    let pi: f32 = 3.14;
    let euler: Box<f32> = Box::new(2.72);
    let cool_name: String = String::from("quantum");
    
    println!("{pi}, {euler}, {cool_name}"); // OK
    
    let pi_copy: f32 = pi; // COPY
    let euler_ref: Box<f32> = euler; // MOVE
    let cool_name_ref: String = cool_name; // MOVE
    
    println!("{pi} = {pi_copy}"); // OK
    println!("{euler} = {euler_ref}"); // ERROR
}
```
<img src="src/memory/rust_mem1.png" alt="Rust memory - stack vs heap" width=95% style="margin-top: -5%;">


### Rust - copy vs move

```rs[3-6]
fn main() {
    let pi: f32 = 3.14;
    let euler: Box<f32> = Box::new(2.72);
    let cool_name: String = String::from("quantum");
    
    println!("{pi}, {euler}, {cool_name}"); // OK
    
    let pi_copy: f32 = pi; // COPY
    let euler_ref: Box<f32> = euler; // MOVE
    let cool_name_ref: String = cool_name; // MOVE
    
    println!("{pi} = {pi_copy}"); // OK
    println!("{euler} = {euler_ref}"); // ERROR
}
```
<img src="src/memory/rust_mem2.png" alt="Rust memory - stack vs heap" width=95% style="margin-top: -5%;">


### Rust - copy vs move

```rs[8-10]
fn main() {
    let pi: f32 = 3.14;
    let euler: Box<f32> = Box::new(2.72);
    let cool_name: String = String::from("quantum");
    
    println!("{pi}, {euler}, {cool_name}"); // OK
    
    let pi_copy: f32 = pi; // COPY
    let euler_ref: Box<f32> = euler; // MOVE
    let cool_name_ref: String = cool_name; // MOVE
    
    println!("{pi} = {pi_copy}"); // OK
    println!("{euler} = {euler_ref}"); // ERROR
}
```
<img src="src/memory/rust_mem3.png" alt="Rust memory - stack vs heap" width=95% style="margin-top: -5%;">


### Rust - copy vs move

```rs[12-13]
fn main() {
    let pi: f32 = 3.14;
    let euler: Box<f32> = Box::new(2.72);
    let cool_name: String = String::from("quantum");
    
    println!("{pi}, {euler}, {cool_name}"); // OK
    
    let pi_copy: f32 = pi; // COPY
    let euler_ref: Box<f32> = euler; // MOVE
    let cool_name_ref: String = cool_name; // MOVE
    
    println!("{pi} = {pi_copy}"); // OK
    println!("{euler} = {euler_ref}"); // ERROR
}
```
<img src="src/memory/rust_mem4.png" alt="Rust memory - stack vs heap" width=95% style="margin-top: -5%;">


### Rust - deallocating heap data

```rs[2-3]
fn main() {
    let year: u16 = 2024;
    let era: String = String::from("AD");
    let auc: u16 = convert_to_AUC(year, era);
    println!("Today is {} AUC ({} {})", auc, year, era); // E
}

fn convert_to_AUC(yr: u16, era: String) -> u16 {
    // AUC - ab urbe condita
    // years since the foundation of Rome
    if era == "AD" { return 753 + yr };
    753 - yr + 1
}
```
<img src="src/memory/rust_mem5.png" alt="Rust memory - stack vs heap" width=95% style="margin-top: -5%;">


### Rust - deallocating heap data

```rs[8-11]
fn main() {
    let year: u16 = 2024;
    let era: String = String::from("AD");
    let auc: u16 = convert_to_AUC(year, era);
    println!("Today is {} AUC ({} {})", auc, year, era); // E
}

fn convert_to_AUC(yr: u16, era: String) -> u16 {
    // AUC - ab urbe condita
    // years since the foundation of Rome
    if era == "AD" { return 753 + yr };
    753 - yr + 1
}
```
<img src="src/memory/rust_mem6.png" alt="Rust memory - stack vs heap" width=95% style="margin-top: -5%;">


### Rust - deallocating heap data

```rs[4-5]
fn main() {
    let year: u16 = 2024;
    let era: String = String::from("AD");
    let auc: u16 = convert_to_AUC(year, era);
    println!("Today is {} AUC ({} {})", auc, year, era); // E
}

fn convert_to_AUC(yr: u16, era: String) -> u16 {
    // AUC - ab urbe condita
    // years since the foundation of Rome
    if era == "AD" { return 753 + yr };
    753 - yr + 1
}
```
<img src="src/memory/rust_mem7.png" alt="Rust memory - stack vs heap" width=95% style="margin-top: -5%;">