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
```

Example:

```rust
use pt100::{resistance_to_temperature, temperature_to_resistance};
fn main() {
    // Example 1: Convert resistance to temperature
    let resistance = 100000; // 100Ω = 100000 mΩ
    let temperature = resistance_to_temperature(resistance);
    println!("Resistance: {} mΩ ({:.2}Ω) → Temperature: {} m°C ({:.1}°C)", 
             resistance, 
             resistance as f32 / 1000.0,
             temperature, 
             temperature as f32 / 1000.0);
    // Output: Resistance: 100000 mΩ (100.00Ω) → Temperature: 0 m°C (0.0°C)

    // Example 2: Convert temperature to resistance
    let temp = 25000; // 25°C = 25000 m°C
    let res = temperature_to_resistance(temp);
    println!("Temperature: {} m°C ({:.1}°C) → Resistance: {} mΩ ({:.3}Ω)",
             temp,
             temp as f32 / 1000.0,
             res,
             res as f32 / 1000.0);
    // Output: Temperature: 25000 m°C (25.0°C) → Resistance: 109734 mΩ (109.734Ω)
}

```