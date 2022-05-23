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



## Log4rs
https://docs.rs/log4rs/latest/log4rs/


## Env_logger
https://crates.io/crates/env_logger

```toml
env_logger = "0.9.0"
```


```rust
#[macro_use]
extern crate log;

fn main() {
    env_logger::init();

    info!("starting up");

    // ...
}
```