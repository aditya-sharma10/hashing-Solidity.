# 🔐Hashing-Solidity

+ this repository demonstrates how to use cryptographic hashing functions in Solidity. Hashing is an essential concept in blockchain and smart contracts, enabling data integrity, verification, and security.

+ The repo provides clean, beginner-friendly examples of common Solidity hashing functions such as:

+ keccak256 (Ethereum’s default hashing algorithm, based on SHA-3)

+ sha256 (commonly used in Bitcoin and cross-chain applications)

+ ripemd160 (used for shorter hash outputs, often in address generation)

---
## 📌Why Hashing in Solidity?

Hashing is widely used in blockchain and Solidity smart contracts for:

✅ Data Integrity → Ensuring stored or transmitted data is not tampered with.

✅ Digital Signatures → Used in verifying ownership and secure transactions.

✅ Commit-Reveal Schemes → Allowing fair games, lotteries, and sealed bidding.

✅ Unique Identifiers → Creating non-reversible identifiers for sensitive data.

✅ Access Control → Securely storing hashed passwords or keys.
---
---
## 📂Project Structure
```
Hashing-Solidity/
│── src/
│   └── Hashing.sol     # Solidity contract with hashing examples
│── test/
│   └── Hashing.t.sol   # Foundry test cases for hashing
│── script/
│   └── Deploy.s.sol    # Example deployment script
│── README.md           # Documentation
```
---
## 🧑‍💻Example Usage
Solidity Contract
```
// SPDX-License-Identifier: MIT
pragma solidity ^0.8.20;

contract Hashing {
    function hashWithKeccak(string memory _data) public pure returns (bytes32) {
        return keccak256(abi.encodePacked(_data));
    }

    function hashWithSHA(string memory _data) public pure returns (bytes32) {
        return sha256(abi.encodePacked(_data));
    }

    function hashWithRIPEMD(string memory _data) public pure returns (bytes20) {
        return ripemd160(abi.encodePacked(_data));
    }
}
```
---

## Sample Test (Foundry)
```
pragma solidity ^0.8.20;

import "forge-std/Test.sol";
import "../src/Hashing.sol";

contract HashingTest is Test {
    Hashing hashing;

    function setUp() public {
        hashing = new Hashing();
    }

    function testKeccak() public {
        bytes32 hash = hashing.hashWithKeccak("Hello");
        assertEq(hash, keccak256(abi.encodePacked("Hello")));
    }
}
```

🚀 Getting Started

1️⃣ Install Foundry
```
curl -L https://foundry.paradigm.xyz | bash
foundryup
```
2️⃣ Clone the repository
```
git clone https://github.com/yourusername/Hashing-Solidity.git
cd Hashing-Solidity
```
3️⃣ Build & Test
```
forge build
forge test -vv
```
---
> 📖 Learn More

+ Solidity Docs – Cryptographic Functions

+ Ethereum Yellow Paper
---
🏷️ License

This project is licensed under the MIT License – free to use and modify.
