# Guessing Game Developer Overview

This project is a simple command-line guessing game implemented in Rust. It challenges players to guess a randomly generated number between 1 and 100, providing feedback on whether their guess is too high or too low until the correct number is found.

## Architecture

The application operates as a single Rust binary. It utilizes the `rand` crate to generate a secret number upon startup. The core game loop continuously prompts the user for input, parses the guess (handling non-numeric input by prompting again), and compares it against the secret number using `std::cmp::Ordering`. Feedback ('Too Small!', 'Too Big!', 'You Win!') is provided, and the loop terminates only when the correct number is guessed, indicating a win condition.

## Key Files

*   **`Cargo.toml`**: Defines the Rust project's metadata. It names the project `guessing_game`, specifies `version = "0.1.0"` and `edition = "2018"`. It declares `rand = "0.3.14"` as a primary dependency, essential for random number generation within the game.
*   **`src/main.rs`**: Contains the entire game logic. It initializes a `secret_number` using `rand::thread_rng().gen_range(1, 101)`. The `main` function enters an infinite `loop` where it:
    *   Prompts for user input (`io::stdin().read_line`).
    *   Parses the input into a `u32`, using a `match` statement to `continue` the loop on `Err` (invalid input) or bind `Ok(num)` to the `guess` variable.
    *   Compares `guess` with `secret_number` using `guess.cmp(&secret_number)`.
    *   Prints 'Too Small!', 'Too Big!', or 'You Win!' based on `Ordering::Less`, `Ordering::Greater`, or `Ordering::Equal` respectively.
    *   Breaks the loop upon `Ordering::Equal`.

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