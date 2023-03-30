This is zkSync Era sample contract implemented on windows vscode using hardhat.

Prerequisites:

	- Latest version of node.js installed
	- Docker Desktop installed
	- npm package manager
	- Metamask wallet with zkSync testnet Eth(0.01), add the network 'zkSync Era testnet' from chainlist(https://chainlist.org/chain/280?search=zkSync&testnets=true).

<b>Follow these steps:</b>

1. Initialize the project by opening Vscode and creating new folder 'sample-contract'. Then, install the dependencies by running the following commands in your terminal:
		
		npm init -y
		npm i -D typescript ts-node ethers@^5.7.2 zksync-web3 hardhat @matterlabs/hardhat-zksync-solc @matterlabs/hardhat-zksync-deploy
	Above 2 commands will install necessary files and it will appear in your sample-contract folder(node modules folder, package, package.lock, articrafts-zk, cache-zk).

2. Download and import  "contracts" folder, "deploy" folder and hardhat.config file in sample-contract folder.

3. Create a file name '.secret' in sample-contract folder and paste your Metamask wallet private key. Make sure to use your unused burner wallet, not main wallet. Save and close.

4. Compile the contract with the following command:
		npx hardhat compile
	This step will compile your contracts/greeter.sol file and result shows "Successfully compiled 1 Solidity file".

5. Deploy the contract with following command:
		npx hardhat deploy-zksync
	This step will deploy contract with help of deploy/deploy.ts file and result shows "Greeter was deployed to <contract address>".

	Congrats! You've successfully deployed the sample contract on zkSync testnet.

6. The contract address you got from step-5 you can check by visiting zkSync explorer(https://goerli.explorer.zksync.io/) and pasting contract address in search bar.

7. Now, verify the contract by following commands. Go to vscode terminal and implement the following command:

		npm i -D @matterlabs/hardhat-zksync-verify @nomiclabs/hardhat-etherscan
		npx hardhat verify --network zkSyncTestnet <paste contract hash from step-5> "Hi there!"
		 
	This will verify your contract and result shows "Nothing to compile. Your verification ID is: 0000. Contract successfully verified on zkSync block explorer!"




