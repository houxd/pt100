# PT100 Temperature Sensor Library

A Rust library for converting between PT100 resistance values and temperatures.

## Features

- Convert PT100 resistance (mΩ) to temperature (m°C)
- Convert temperature (m°C) to PT100 resistance (mΩ)
- Temperature range: -200°C to +850°C
- High precision lookup table with 1°C intervals
- `no_std` compatible

## Usage

Add this to your `Cargo.toml`:

```toml
[dependencies]
pt100 = "0.1.0"