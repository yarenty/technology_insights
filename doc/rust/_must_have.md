# Cargo.toml

```yaml
[dependencies]
chrono = "0.4"
log = "0.4.16"
simplelog = "0.12.0"
tokio = { version = "1", features = ["full"] }
serde = { version = "1.0", features = ["derive"] }
```


## Log

```rust

use log::{info,warn, debug, trace};
#[macro_use] extern crate log;
extern crate simplelog;

use simplelog::*;


#[tokio::main]
async fn main() -> Result<()> {
    // terminal only output:
    TermLogger::init(LevelFilter::Debug, Config::default(), TerminalMode::Mixed, ColorChoice::Auto).unwrap();

    // both terminal and log file
    CombinedLogger::init(
        vec![
            TermLogger::new(LevelFilter::Warn, Config::default(), TerminalMode::Mixed, ColorChoice::Auto),
            WriteLogger::new(LevelFilter::Info, Config::default(), File::create("my_rust_binary.log").unwrap()),
        ]
    ).unwrap();

}


```

## Log

https://github.com/drakulix/simplelog.rs


## Chrono


## Tokio

