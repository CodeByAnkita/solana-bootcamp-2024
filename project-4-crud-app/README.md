# Solana CRUD App

This project demonstrates a basic on-chain CRUD (Create, Read, Update, Delete) decentralized application (dApp) on the Solana blockchain. The application is a journal dApp where users can manage journal entries via a user interface that interacts with a Solana program.

This project was created using the [create-solana-dapp](https://github.com/solana-developers/create-solana-dapp) generator.

---

## Getting Started

### Prerequisites

Before running this project, ensure you have the following installed:

- **Node.js**: Version 18.18.0 or higher
- **Rust**: Version 1.70.0 or higher
- **Anchor CLI**: Version 0.29.0 or higher
- **Solana CLI**: Version 1.17.0 or higher

---

## Installation and Setup

### Clone the Repository

```bash
git clone <repo-url>
cd <repo-name>
```

### Install Dependencies

Navigate to the root directory and install dependencies:

```bash
npm install
```

### Start the Web Application

```bash
npm run dev
```

---

## Application Structure

### Anchor (Solana Program)

The Solana program is written in Rust using the Anchor framework. The program logic for the journal dApp can be found in the file:

```
anchor/programs/src/lib.rs
```

#### Key Commands

- **Sync the Program ID**:

  This command creates a new keypair in the `anchor/target/deploy` directory, updates the Anchor config file, and modifies the `declare_id!` macro in the `lib.rs` file to match the new program ID. You must manually update the constant in `anchor/lib/counter-exports.ts` to reflect this ID.

  ```bash
  npm run anchor keys sync
  ```

- **Build the Program**:

  ```bash
  npm run anchor-build
  ```

- **Start a Local Validator and Deploy the Program**:

  ```bash
  npm run anchor-localnet
  ```

- **Run Tests**:

  ```bash
  npm run anchor-test
  ```

- **Deploy to Devnet**:

  ```bash
  npm run anchor deploy --provider.cluster devnet
  ```

### Web Application

The web application is a React-based frontend that uses the Anchor-generated client to interact with the deployed Solana program.

#### Key Commands

- **Start the Web Application**:

  ```bash
  npm run dev
  ```

- **Build the Web Application**:

  ```bash
  npm run build
  ```

---

## Step-by-Step Instructions

### Initialize the Local Environment

1. Start the local Solana validator:

   ```bash
   solana-test-validator
   ```

2. Deploy the Anchor program to the local validator:

   ```bash
   cd anchor
   anchor deploy --provider.cluster localnet
   anchor keys sync
   ```

### Start the Web Application

1. Navigate to the web folder:

   ```bash
   cd web
   ```

2. Run the application in development mode:

   ```bash
   npm run dev
   ```

---

## Commands Overview

### Anchor Program

- **Build**:

  ```bash
  npm run anchor-build
  ```

- **Deploy Locally**:

  ```bash
  npm run anchor-localnet
  ```

- **Sync Keys**:

  ```bash
  npm run anchor keys sync
  ```

- **Deploy to Devnet**:

  ```bash
  npm run anchor deploy --provider.cluster devnet
  ```

### Web Application

- **Start Development Server**:

  ```bash
  npm run dev
  ```

- **Build Production Version**:

  ```bash
  npm run build
  ```

---

## Project Workflow

1. **Generate the dApp**:

   Use the `create-solana-dapp` generator to initialize your project:

   ```bash
   npx create-solana-dapp
   ```

   Select the following options:
   - Project Name
   - Framework: Next.js
   - Styling: Tailwind CSS
   - Backend: Anchor

2. **Run Local Validator**:

   ```bash
   solana-test-validator
   ```

3. **Deploy the Program Locally**:

   Navigate to the `anchor` directory and run:

   ```bash
   anchor deploy --provider.cluster localnet
   anchor keys sync
   ```

4. **Start the Web App**:

   Navigate to the `web` directory and run:

   ```bash
   npm run dev
   ```

---

## Notes

- **Updating the Program ID**:
  Ensure that the constant in `anchor/lib/counter-exports.ts` matches the program ID from `anchor/target/deploy`.

- **Testing Locally**:
  Use the `solana-test-validator` to emulate the Solana blockchain locally.

- **Deploying to Devnet**:
  Update your Solana CLI configuration to point to the Devnet cluster if required:

  ```bash
  solana config set --url https://api.devnet.solana.com
  ```

---

## Conclusion

This CRUD app demonstrates how to build and deploy a basic dApp on Solana using Anchor and React. By following the steps above, you can explore the functionality of the Solana blockchain and create on-chain applications.

