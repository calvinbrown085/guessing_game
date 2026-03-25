# Guessing Game

This project is a simple command-line guessing game implemented in Rust. Players attempt to guess a randomly generated number between 1 and 100, receiving hints if their guess is too high or too low, until they guess correctly.

## Architecture

The application is a single Rust binary leveraging the `rand` crate for secret number generation and `std::io` for console input. The core logic executes within an infinite loop, continuously prompting for guesses, parsing input, comparing the guess to the secret number, and providing immediate feedback. The loop terminates upon a correct guess.

## Key Files

*   **`Cargo.toml`**: Defines the Rust project's metadata, including its name (`guessing_game`), version, authors, and edition. It declares `rand = "0.3.14"` as a crucial dependency for random number generation.
*   **`src/main.rs`**: Contains all the game logic. It initializes a secret number using `rand::thread_rng().gen_range(1, 101)`. The `main` function then enters a loop to prompt for user input, read and parse the guess into a `u32` (skipping non-numeric input), and compare it against the `secret_number` using `std::cmp::Ordering`. Feedback ("Too Small!", "Too Big!", or "You Win!") is provided, breaking the loop on a win.

## How to Run

To run this guessing game, the Rust toolchain must be installed.

### Prerequisites

*   **Rust Toolchain**: Install Rust by following the instructions on [rust-lang.org](https://www.rust-lang.org/tools/install). `rustup` is the recommended installation method.

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
    This command compiles the project and executes the `guessing_game` binary.