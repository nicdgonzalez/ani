# ANI

Parser for the ANI file format.

## Usage

Use cargo to add the library to your project:

```bash
cargo add --git https://github.com/nicdgonzalez/ani.git
```

## Examples

```rust
use std::fs;

use ani::Ani;

fn main() -> Result<(), Box<dyn std::error::Error>> {
    let mut reader = fs::File::open("/path/to/file.ani")?;
    let ani = Ani::from_reader(&mut reader)?;

    println!("Metadata: {:?}", ani.metadata());
    println!("Header: {:?}", ani.header());
    println!("Rates: {:?}", ani.rates());
    println!("Sequence: {:?}", ani.sequence());
    println!("Frames: {:?}", ani.frames());

    Ok(())
}
```
