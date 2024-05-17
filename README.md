# ZK-SNARK-Designer

## Overview

This project demonstrates the process of creating a zero-knowledge proof (ZKP) using Circom and Hardhat. The project includes writing a correct Circom circuit, compiling it, generating proofs, and deploying a verifier contract to a blockchain testnet. Specifically, the project includes generating a proof for given inputs \( A = 0 \) and \( B = 1 \), and verifying it on the Sepolia or Mumbai Testnet.

## Tools Used

- **Hardhat**: A development environment for Ethereum software.
- **Circom**: A circuit compiler for zero-knowledge proofs.
- **Hardhat-Circom**: A template that integrates Hardhat with Circom to write, compile circuits, and generate proofs and verifiers.

## Project Structure

```
.
├── contracts
│   └── Verifier.sol       # Solidity verifier contract
├── circuits
│   └── circuit.circom     # Circom circuit implementation
├── scripts
│   └── deploy.js          # Deployment script for the verifier contract
├── test
│   └── verifyProof.js     # Test script to call the verifyProof() method
├── input.json             # Input file containing values for A and B
├── README.md              # Project documentation
├── hardhat.config.js      # Hardhat configuration file
└── package.json           # Project dependencies
```

## Project Rubric

To successfully complete the Final Challenge, your project should:

1. **Write a Correct `circuit.circom` Implementation**
   - Implement the zero-knowledge circuit in Circom.
   - Ensure the circuit logic correctly represents the computation you intend to prove knowledge of.

2. **Compile the Circuit**
   - Use Hardhat-Circom to compile the Circom circuit.
   - Generate necessary circuit intermediaries such as R1CS and WASM files.

3. **Generate a Proof**
   - Utilize the compiled circuit to generate a proof using the given inputs \( A = 0 \) and \( B = 1 \).

4. **Deploy a Solidity Verifier to Sepolia or Mumbai Testnet**
   - Write a Solidity verifier contract and deploy it to the chosen testnet.
   - Use Hardhat scripts for deployment.

5. **Verify the Proof**
   - Call the `verifyProof()` method on the deployed verifier contract.
   - Assert that the output of `verifyProof()` is `true`.

## Steps to Run the Project

1. **Clone the Repository**

2. **Install Dependencies**

   ```bash
   npm install
   ```

3. **Write and Compile the Circuit**

   - Write your circuit logic in `circuits/circuit.circom`.
   - Compile the circuit:

     ```bash
     npx hardhat circom
     ```

4. **Generate the Proof**

   - Ensure you have the necessary inputs in `input.json`.
   - Generate the proof:

     ```bash
     npx hardhat generate-proof
     ```

5. **Deploy the Verifier Contract**

   - Deploy the verifier contract to Sepolia or Mumbai Testnet:

     ```bash
     npx hardhat run scripts/deploy.js --network sepolia
     ```

6. **Verify the Proof**

   - Run the verification script:

     ```bash
     npx hardhat test
     ```

## Notes

- Ensure you have a funded account for the deployment on the chosen testnet.
- Update the `hardhat.config.js` file with the correct network configurations and account details.
- The `verifyProof.js` script should be updated to point to the deployed contract address and correctly parse the proof.

## Conclusion

This project demonstrates the end-to-end process of creating and verifying a zero-knowledge proof using Circom and Hardhat. By following the steps outlined, you will gain hands-on experience with ZKP technology and smart contract deployment.
