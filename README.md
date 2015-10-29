# chemfiles.rs

[![Build Status](https://travis-ci.org/chemfiles/chemfiles.rs.svg?branch=master)](https://travis-ci.org/chemfiles/chemfiles.rs)
[![codecov.io](https://codecov.io/github/chemfiles/chemfiles.rs/coverage.svg?branch=master)](https://codecov.io/github/chemfiles/chemfiles.rs?branch=master)
[![Documentation Status](https://img.shields.io/badge/docs-latest-brightgreen.svg)](http://chemfiles.github.io/chemfiles.rs/chemfiles/index.html)

Rust binding for the [chemfiles](https://github.com/chemfiles/chemfiles) library. The
documentation is available [here](http://chemfiles.github.io/chemfiles.rs/chemfiles).

## Usage

Add this to your `Cargo.toml` file:

```toml
[dependencies.chemfiles]
git = "https://github.com/chemfiles/chemfiles.rs"
```

And then use `chemfiles` in your project:

```rust
extern crate chemfiles;
```

Here is a simple usage example. Please see the `examples` folder for more examples.

```rust
extern crate chemfiles;
use chemfiles::{Trajectory, Frame};

fn main() {
    let mut trajectory = Trajectory::new("filename.xyz").unwrap();
    let mut frame = Frame::new(0).unwrap();

    trajectory.read(&mut frame).unwrap();

    println!("There are {} atoms in the frame", frame.natoms().unwrap())

    let positions = frame.positions().unwrap();

    // Do awesome things with the positions here !
}
```

## Bug reports, feature requests

Please report any bug you find and any feature you may want as a [github issue](https://github.com/chemfiles/chemfiles.rs/issues/new).
