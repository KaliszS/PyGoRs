## Functions


### Function definition and call

<div class="svglang">
  <object data="src/functions/function_py.svg"></object>
  <object data="src/functions/function_rs.svg"></object>
  <object data="src/functions/function_go.svg"></object>
</div>


### Rust - macros

```rs
// macro is expanded into source code and gets compiled
// C macro -> string preprocessing, Rust macro -> AST
macro_rules! create_function {
  // `ident` designator is used for variable/function names
  ($func_name:ident) => {
    fn $func_name() {
      println!("You called {:?}()", stringify!($func_name));
    }
  };
}

create_function!(foo);

```


### Rust - macros

```rs
macro_rules! calculate {
  (eval $e:expr) => {
    {
      let val: usize = $e; // force type
      println!("{} = {}", stringify!{$e}, val);
    }
  };
}

calculate! {
  eval 1 + 2 // eval used like a Rust keyword
}
```


### Variadic functions

<div class="svglang">
  <object data="src/functions/variadic_py.svg"></object>
  <object data="src/functions/variadic_rs.svg"></object>
  <object data="src/functions/variadic_go.svg"></object>
</div>