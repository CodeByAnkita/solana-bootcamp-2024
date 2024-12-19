# Swap Program

This project demonstrates how to create a swap program on the Solana blockchain. The swap program allows users to exchange tokens securely and efficiently.

Follow the instructions below to set up the project and test it locally.

## Prerequisites

Before starting, ensure you have the following installed:

1. **Rust and Cargo**: [Install Rust](https://www.rust-lang.org/tools/install)
2. **Anchor CLI**: [Install Anchor](https://book.anchor-lang.com/getting_started/installation.html)
3. **Solana CLI**: [Install Solana CLI](https://docs.solana.com/cli/install-solana-cli-tools)
4. **Node.js**: [Install Node.js](https://nodejs.org/) (for frontend integration)

Ensure your Solana CLI and Anchor CLI versions are up to date:
```bash
solana --version
anchor --version
```

## Project Setup

### 1. Initialize the Project

Create a new Anchor project using the `multiple` template:
```bash
anchor init swap --template=multiple
```
This command initializes a new project named `swap` with a pre-configured workspace for multiple programs.

### 2. Navigate to the Project Directory

Change into the project directory:
```bash
cd swap
```

### 3. Build the Project

Compile the project:
```bash
anchor build
```
This will build the Rust programs in the `programs` directory and generate the corresponding IDL files.

### 4. Run Tests

Run the provided tests to verify the program:
```bash
anchor test
```
This command executes the test cases in the `tests` directory and deploys the program to a local Solana cluster for testing.

### Solana Network Configuration
- **Set Solana Cluster**:
  ```bash
  solana config set --url <cluster-url>
  ```
  Example for Devnet:
  ```bash
  solana config set --url https://api.devnet.solana.com
  ```

- **Check Solana Configuration**:
  ```bash
  solana config get
  ```

### Anchor Commands
- **Deploy the Program**:
  ```bash
  anchor deploy
  ```
- **Upgrade the Program**:
  ```bash
  anchor upgrade --program-id <PROGRAM_ID> <PROGRAM_FILEPATH>
  ```

### Workspace Commands
- **Clean the Workspace**:
  ```bash
  cargo clean
  ```
- **Run Linter**:
  ```bash
  cargo clippy
  ```
- **Check Formatting**:
  ```bash
  cargo fmt
  ```

## Troubleshooting

### Common Issues

#### 1. `anchor build` fails with dependency errors
Ensure your dependencies are correctly defined in `Cargo.toml`. If the error relates to `anchor-spl`, add the dependency:
```toml
[dependencies]
anchor-lang = "0.30.1"
anchor-spl = "0.30.0"
```

#### 2. Lock file version mismatch
If you encounter an error like `lock file version 4 requires -Znext-lockfile-bump`, ensure your Rust version is up to date:
```bash
rustup update
```

#### 3. Solana CLI issues
Ensure your Solana CLI version is compatible with Anchor:
```bash
solana --version
```

## Resources

- [Anchor Documentation](https://book.anchor-lang.com/)
- [Solana Documentation](https://docs.solana.com/)
- [YouTube Video](https://www.youtube.com/watch?v=amAq-WHAFs8&t=15922s)


