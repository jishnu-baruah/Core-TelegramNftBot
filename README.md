# TelegramNFT

TelegramNFT is a lightweight ERC-721 smart contract built on Solidity, enabling the minting of NFTs with custom metadata URIs. It supports authorization logic for specific minters and includes event emission for tracking mints on-chain.

## 🧾 Contract Details

- **Contract Name:** `TelegramNFT`
- **Token Name:** TelegramNFT
- **Token Symbol:** TGNFT
- **Standard:** ERC-721 (with URI Storage)
- **Deployed At:** [`0x1fbA70E7A768448EC1Bf34DC53558b47De7b872c`](https://etherscan.io/address/0x1fbA70E7A768448EC1Bf34DC53558b47De7b872c)
- **Explorer Screenshot:**  
  ![Explorer Screenshot](./image.png)

## 🔐 Roles

- **Owner:** Can authorize or revoke minters.
- **Authorized Minters:** Can mint NFTs using the `mintNFT` function.

## 🔧 Functions

### `authorizeMinter(address minter)`
Grants minting privileges to an address. Only callable by the owner.

### `revokeMinter(address minter)`
Revokes minting rights from a minter. Only callable by the owner.

### `mintNFT(address to, string memory uri)`
Mints an NFT with a specified token URI to a recipient address. Only callable by authorized minters.

### `NFTMinted`
An event emitted upon successful NFT minting.

## 🔒 Access Control

| Function         | Accessible By           |
|------------------|--------------------------|
| `authorizeMinter` | Owner                    |
| `revokeMinter`    | Owner                    |
| `mintNFT`         | Authorized Minters       |

## 📦 Dependencies

- [OpenZeppelin Contracts](https://github.com/OpenZeppelin/openzeppelin-contracts)
  - ERC721URIStorage
  - Ownable
  - Counters

Install dependencies via npm:

```bash
npm install @openzeppelin/contracts
🧪 Deployment & Testing
You can deploy and test the contract using tools like Hardhat or Foundry.

Example deployment snippet with Hardhat:

javascript
Copy
Edit
const TelegramNFT = await ethers.getContractFactory("TelegramNFT");
const telegramNFT = await TelegramNFT.deploy(ownerAddress);
await telegramNFT.deployed();
📸 Blockchain Explorer
Check out the deployed contract on the explorer:

🔗 View Contract on Etherscan


📝 License
This project is licensed under the MIT License.

yaml
Copy
Edit

---

Let me know if you'd like a Hardhat deployment script or a frontend integration snippet too!
