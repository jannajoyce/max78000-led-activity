This project demonstrates basic GPIO control on the **MAX78000FTHR** by driving **8 LEDs** and using **1 push button** to switch between two LED animation patterns.
The activity helps students understand embedded programming, GPIO configuration, debouncing, and pattern sequencing.

## Features

- Controls 8 individual LEDs using GPIO output pins
- Reads 1 push button using MAX78000’s PB driver
- Two LED animation modes:
   1. Odd–Even Blinking Pattern
   2. Larson Scanner (Knight Rider Effect)

- Button press toggles between modes
- Built-in software debouncing for stable button input
- Fully compatible with MAX78000 SDK

## Hardware Requirements

- MAX78000FTHR Development Board
- 8 LEDs
- 8 current-limiting resistors (68Ω)
- 1 Push Button
- Breadboard + jumper wires

## Wiring Overview

### LED Connections

Each LED is connected to a specific GPIO pin as defined in the code:

| LED  | Port  | Pin |
| ---- | ----- | --- |
| LED1 | GPIO1 | P6  |
| LED2 | GPIO0 | P9  |
| LED3 | GPIO0 | P8  |
| LED4 | GPIO0 | P11 |
| LED5 | GPIO0 | P19 |
| LED6 | GPIO3 | P1  |
| LED7 | GPIO0 | P16 |
| LED8 | GPIO0 | P17 |

Each LED should be wired:

### Push Button

- Connect the push button to P2_3
- Uses internal pull-up, reads 1 when pressed


## Program Behavior

- All LEDs are configured as outputs.
- All LEDs start in the OFF state.
- Push button input is initialized.
- Default animation mode is **Odd–Even Pattern**.

## LED Patterns

### 1. Odd–Even Pattern

- LEDs at indexes 0, 2, 4, 6 turn ON → pause
- LEDs at indexes 1, 3, 5, 7 turn ON → pause
- Repeats continuously

### 2. Larson Scanner Pattern

- One LED sweeps left to right
- Reverses direction at the edges
- Creates the “Knight Rider” effect

## Switching Patterns

- The button press triggers a **rising-edge detection
- `mode ^= 1` toggles the active LED pattern
- A small delay is used for debouncing

## File Description

main.c – Contains GPIO setup, button handling, and LED pattern logic.

## How to Run

1. Import project into the MAX78000 SDK environment
2. Build the project
3. Flash the firmware to the MAX78000FTHR
4. Connect LEDs and button
5. Observe the LED animations
6. Press the button to change patterns

## Educational Purpose

This activity teaches:

- GPIO configuration
- Push button debouncing
- State-based programming
- LED pattern generation
- Embedded logic control on MAX78000
