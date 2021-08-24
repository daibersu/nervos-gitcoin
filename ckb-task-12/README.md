                                    Document Porting An Existing Ethereum DApp To Polyjuice

1. Setup the Godwoken Testnet Network in MetaMask


first, you will need to configure a new custom RPC. 

From the network selection dropdown, select "Custom RPC".

![metamask-network-menu](https://user-images.githubusercontent.com/88998318/130059264-15e7a987-69de-4f6d-b926-8274f61e1ba7.png)

MetaMask Network Menu
From there you will be presented with a form to specify the network settings.

MetaMask Add Network
Enter the following details.


![metamask-networks2](https://user-images.githubusercontent.com/88998318/130059285-d2aa9826-de77-4b51-8bbb-96ef7d8511c7.png)



```
Network Name: Godwoken Testnet

RPC URL: https://godwoken-testnet-web3-rpc.ckbapp.dev

Chain ID: 71393

Currency Symbol: <Leave Empty>
  
Block Explorer URL: <Leave Empty>
```

  
2. clone the Ethereum dapp and a some operate 
  


```
cd ~/projects
  
git clone git@github.com:oceanSxq/nervos-gen-nft.git 
  
cd nervos-gen-nft
  
yarn
  
yarn build
  
yarn start:ganache
  
yarn ui
```

open a browser tab to http://localhost:3000 to view the dApp UI!
  
  

3. Install Polyjuice Dependencies
  

**cd ~/projects/nervos-gen-nft**
  

```
yarn add @polyjuice-provider/web3@0.0.1-rc7 nervos-godwoken-integration@0.0.6
```

  
@polyjuice-provider/web3 is a custom Polyjuice web3 provider.
  
It is required for interaction with Nervos' Layer 2 smart contracts.
  
nervos-godwoken-integration is a tool that can generate Polyjuice address based on your Ethereum address. 
  
You might be required to use Polyjuice address if you store values mapped to addresses in your contracts.
  
4. Configure the Web3 Provider for the Polyjuice Web3 Provider

Here is the contents of the file

**~/projects/nervos-gen-nft/src/config.ts**

that we just created:


  
  
```
export const CONFIG = {
   WEB3_PROVIDER_URL: 'https://godwoken-testnet-web3-rpc.ckbapp.dev',
    ROLLUP_TYPE_HASH: '0x4cc2e6526204ae6a2e8fcf12f7ad472f41a1606d5b9624beebd215d780809f6a',
    ETH_ACCOUNT_LOCK_CODE_HASH: '0xdeec13a7b8e100579541384ccaf4b5223733e4a5483c3aec95ddc4c1d5ea5b22'
  };
```

  
We will use these config values in a moment, but first we need to import a few dependencies.
  
We will update the main UI in the file

**~/projects/nervos-gen-nft/src/ui/app.tsx.**

Next, we add the following lines in the main dependency importation section of the file.
  


```
import { PolyjuiceHttpProvider } from '@polyjuice-provider/web3';
  
  
import { CONFIG } from '../config';
```

  
  
This imports the Polyjuice Web3 Provider, which we will use in a moment, and the config file that we just created.

Next we prepare a few constants, create the Polyjuice Provider, and use the Polyjuice Provider with a Web3 instance.
  
    const godwokenRpcUrl = CONFIG.WEB3_PROVIDER_URL;
    const providerConfig = {
    rollupTypeHash: CONFIG.ROLLUP_TYPE_HASH,
  
    ethAccountLockCodeHash: CONFIG.ETH_ACCOUNT_LOCK_CODE_HASH,
  
    web3Url: godwokenRpcUrl};
    const provider = new PolyjuiceHttpProvider(godwokenRpcUrl, providerConfig);
    const web3 = new Web3(provider);
    
The above code is a Web3 instance using a Polyjuice Web3 Provider. We will just call it "Polyjuice Web3" for short. 
We need to take this code and replace the existing Ethereum Web3 instance. 
In app.tsx, locate the existing Web3 instance, which should match the line below.

const web3 = new Web3((window as any).ethereum);
Delete this line, and replace it with the Polyjuice Web3 code from above. Now our application is setup to communicate with Polyjuice using Web3!

5. Set High Gas Limit
  
Open the file 
```
~/projects/nervos-gen-nft/src/lib/contracts/SimpleStorageWrapper.ts
```
 

First, we define a simple object that contains the gas property used by MetaMask.


```
const DEFAULT_SEND_OPTIONS = {
    gas: 6000000
};
```

This can be added in the top region of the file, and we will be using this constant in several other places.

We will be adding it into the object passed to send() :


```
this.contract.methods.awardItem(fromAddress, imgUrl).send({
            ...DEFAULT_SEND_OPTIONS,
            from: fromAddress
        });
```

  
6. Display Polyjuice Address in Your Application
Every Ethereum address can be translated into a Polyjuice address on Nervos' Layer 2. This can be done using the AddressTranslator class.
We will show the basic code here, but we will not cover the necessary changes for React to display it.

**import { AddressTranslator } from 'nervos-godwoken-integration';**
  
We can then use the following code to find the Polyjuice address.


```
const addressTranslator = new AddressTranslator();
  
const polyjuiceAddress = addressTranslator.ethAddressToGodwokenShortAddress(ethereumAddress);
```

  
7. completed , View your dapp and start ui.


```
cd nervos-gen-nft
yarn
yarn build
yarn ui.
```

you can see the UI server at http://localhost:3000, 

now you can open it in a browser. Once your browser is open, change your MetaMask network to Godwoken Testnet, which we setup earlier in this guide.

  <img width="1302" alt="task7-1" src="https://user-images.githubusercontent.com/88998318/130059181-effc02b1-ca23-4426-9ee1-7116fe417a34.png">

