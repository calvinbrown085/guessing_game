# Guessing Game

This project is a simple command-line guessing game implemented in Rust. Players attempt to guess a randomly generated number between 1 and 100, receiving hints if their guess is too high or too low, until they guess correctly.

## Architecture

The application is a single Rust binary that leverages the `rand` crate for generating the secret number and `std::io` for handling user input from the console. The core logic operates within an infinite loop, continuously prompting for guesses, parsing input, comparing the guess to the secret number, and providing immediate feedback. The loop terminates once the correct number is guessed.

## Key Files

*   **`Cargo.toml`**: This file defines the Rust project's metadata, including its name (`guessing_game`), version, authors, and edition. Crucially, it declares `rand = "0.3.14"` as a dependency, which is used for generating random numbers.
*   **`src/main.rs`**: This is the main source file containing all the game logic. It initializes a secret number using `rand::thread_rng().gen_range(1, 101)`. The `main` function then enters a loop where it prompts the user for input, reads the guess, attempts to parse it into a `u32` integer (skipping non-numeric input), and compares the guess against the `secret_number` using `std::cmp::Ordering`. Based on the comparison, it prints "Too Small!", "Too Big!", or "You Win!" (at which point the game breaks the loop).

## How to Run

To run this guessing game, you need to have the Rust toolchain installed.

### Prerequisites

*   **Rust Toolchain**: Install Rust by following the instructions on [rust-lang.org](https://www.rust-lang.org/tools/install). `rustup` is the recommended way to manage Rust installations.

### Steps

1.  **Clone the Repository**:
    ```bash
    git clone https://github.com/calvinbrown085/guessing_game.git
    ```

2.  **Navigate to the Project Directory**:
    ```bash
    cd guessing_game
    ```

3.  **Run the Game**:
    ```bash
    cargo run
    ```
    This command will compile the project and then execute the `guessing_game` binary.