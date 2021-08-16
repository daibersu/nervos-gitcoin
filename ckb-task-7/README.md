https://gitcoin.co/issue/nervosnetwork/grants/8/100026214
Task Submission
To complete the tasks, add the following materials to a document on your Github and submit for review by the judges (include the link in your Gitcoin submission):

1,Screenshots or video of your application running on Godwoken.

<img width="1056" alt="task7-0" src="https://user-images.githubusercontent.com/88998318/129541932-258b1e6b-1382-4c33-b50f-31126a7ee7f3.png">
<img width="1302" alt="task7-1" src="https://user-images.githubusercontent.com/88998318/129541952-caec819c-7371-4ae1-9cc3-1339088943d3.png">
<img width="1299" alt="task7-2" src="https://user-images.githubusercontent.com/88998318/129541968-32b1da90-4ce2-4a5f-8d22-a3f6f060fbc5.png">
<img width="1172" alt="task7-4" src="https://user-images.githubusercontent.com/88998318/129542001-bece79a8-7262-4d22-98ff-2f51b53746a7.png">



2,Link to the GitHub repository with your application which has been ported to Godwoken. This must be a different application than the one covered in this guide.
 
 https://github.com/oceanSxq/nervos-gen-nft
 
3,If you deployed any smart contracts as part of this tutorial, please provide the transaction hash of the deployment transaction, the deployed contract address, and the ABI of the deployed smart contract. (Provide all in text format.)

Deployed contract address: 0x860b61A3379F925710140c0A1F32173C17D5Dd2F
Deploy transaction hash: 0x43519b1f30df1596415eac48b45babb50dbb5578d761e145a98db0397906e4db
ABI:
[
    {
        "inputs": [ ], 
        "stateMutability": "nonpayable", 
        "type": "constructor"
    }, 
    {
        "anonymous": false, 
        "inputs": [
            {
                "indexed": true, 
                "internalType": "address", 
                "name": "owner", 
                "type": "address"
            }, 
            {
                "indexed": true, 
                "internalType": "address", 
                "name": "approved", 
                "type": "address"
            }, 
            {
                "indexed": true, 
                "internalType": "uint256", 
                "name": "tokenId", 
                "type": "uint256"
            }
        ], 
        "name": "Approval", 
        "type": "event"
    }, 
    {
        "anonymous": false, 
        "inputs": [
            {
                "indexed": true, 
                "internalType": "address", 
                "name": "owner", 
                "type": "address"
            }, 
            {
                "indexed": true, 
                "internalType": "address", 
                "name": "operator", 
                "type": "address"
            }, 
            {
                "indexed": false, 
                "internalType": "bool", 
                "name": "approved", 
                "type": "bool"
            }
        ], 
        "name": "ApprovalForAll", 
        "type": "event"
    }, 
    {
        "anonymous": false, 
        "inputs": [
            {
                "indexed": true, 
                "internalType": "address", 
                "name": "from", 
                "type": "address"
            }, 
            {
                "indexed": true, 
                "internalType": "address",
                "name": "to", 
                "type": "address"
            }, 
            {
                "indexed": true, 
                "internalType": "uint256", 
                "name": "tokenId", 
                "type": "uint256"
            }
        ], 
        "name": "Transfer", 
        "type": "event"
    }, 
    {
        "inputs": [
            {
                "internalType": "address", 
                "name": "to", 
                "type": "address"
            }, 
            {
                "internalType": "uint256", 
                "name": "tokenId", 
                "type": "uint256"
            }
        ], 
        "name": "approve", 
        "outputs": [ ], 
        "stateMutability": "nonpayable", 
        "type": "function"
    }, 
    {
        "inputs": [
            {
                "internalType": "address", 
                "name": "owner", 
                "type": "address"
            }
        ], 
        "name": "balanceOf", 
        "outputs": [
            {
                "internalType": "uint256", 
                "name": "", 
                "type": "uint256"
            }
        ], 
        "stateMutability": "view", 
        "type": "function"
    }, 
    {
        "inputs": [
            {
                "internalType": "uint256", 
                "name": "tokenId", 
                "type": "uint256"
            }
        ], 
        "name": "getApproved", 
        "outputs": [
            {
                "internalType": "address", 
                "name": "", 
                "type": "address"
            }
        ], 
        "stateMutability": "view", 
        "type": "function"
    }, 
    {
        "inputs": [
            {
                "internalType": "address", 
                "name": "owner", 
                "type": "address"
            }, 
            {
                "internalType": "address", 
                "name": "operator", 
                "type": "address"
            }
        ], 
        "name": "isApprovedForAll", 
        "outputs": [
            {
                "internalType": "bool", 
                "name": "", 
                "type": "bool"
            }
        ], 
        "stateMutability": "view", 
        "type": "function"
    }, 
    {
        "inputs": [ ], 
        "name": "name", 
        "outputs": [
            {
                "internalType": "string", 
                "name": "", 
                "type": "string"
            }
        ], 
        "stateMutability": "view", 
        "type": "function"
    }, 
    {
        "inputs": [
            {
                "internalType": "uint256", 
                "name": "tokenId", 
                "type": "uint256"
            }
        ], 
        "name": "ownerOf", 
        "outputs": [
            {
                "internalType": "address", 
                "name": "", 
                "type": "address"
            }
        ], 
        "stateMutability": "view", 
        "type": "function"
    }, 
    {
        "inputs": [
            {
                "internalType": "address", 
                "name": "from", 
                "type": "address"
            }, 
            {
                "internalType": "address", 
                "name": "to", 
                "type": "address"
            }, 
            {
                "internalType": "uint256", 
                "name": "tokenId", 
                "type": "uint256"
            }
        ], 
        "name": "safeTransferFrom", 
        "outputs": [ ], 
        "stateMutability": "nonpayable", 
        "type": "function"
    }, 
    {
        "inputs": [
            {
                "internalType": "address", 
                "name": "from", 
                "type": "address"
            }, 
            {
                "internalType": "address", 
                "name": "to", 
                "type": "address"
            }, 
            {
                "internalType": "uint256", 
                "name": "tokenId", 
                "type": "uint256"
            }, 
            {
                "internalType": "bytes", 
                "name": "_data", 
                "type": "bytes"
            }
        ], 
        "name": "safeTransferFrom", 
        "outputs": [ ], 
        "stateMutability": "nonpayable", 
        "type": "function"
    }, 
    {
        "inputs": [
            {
                "internalType": "address", 
                "name": "operator", 
                "type": "address"
            }, 
            {
                "internalType": "bool", 
                "name": "approved", 
                "type": "bool"
            }
        ], 
        "name": "setApprovalForAll", 
        "outputs": [ ], 
        "stateMutability": "nonpayable", 
        "type": "function"
    }, 
    {
        "inputs": [
            {
                "internalType": "bytes4", 
                "name": "interfaceId", 
                "type": "bytes4"
            }
        ], 
        "name": "supportsInterface", 
        "outputs": [
            {
                "internalType": "bool", 
                "name": "", 
                "type": "bool"
            }
        ], 
        "stateMutability": "view", 
        "type": "function"
    }, 
    {
        "inputs": [ ], 
        "name": "symbol", 
        "outputs": [
            {
                "internalType": "string", 
                "name": "", 
                "type": "string"
            }
        ], 
        "stateMutability": "view", 
        "type": "function"
    }, 
    {
        "inputs": [
            {
                "internalType": "uint256", 
                "name": "tokenId", 
                "type": "uint256"
            }
        ], 
        "name": "tokenURI", 
        "outputs": [
            {
                "internalType": "string", 
                "name": "", 
                "type": "string"
            }
        ], 
        "stateMutability": "view", 
        "type": "function"
    }, 
    {
        "inputs": [
            {
                "internalType": "address", 
                "name": "from", 
                "type": "address"
            }, 
            {
                "internalType": "address", 
                "name": "to", 
                "type": "address"
            }, 
            {
                "internalType": "uint256", 
                "name": "tokenId", 
                "type": "uint256"
            }
        ], 
        "name": "transferFrom", 
        "outputs": [ ], 
        "stateMutability": "nonpayable", 
        "type": "function"
    }, 
    {
        "inputs": [
            {
                "internalType": "address", 
                "name": "owner", 
                "type": "address"
            }, 
            {
                "internalType": "string", 
                "name": "tokenURI", 
                "type": "string"
            }
        ], 
        "name": "awardItem", 
        "outputs": [
            {
                "internalType": "uint256", 
                "name": "", 
                "type": "uint256"
            }
        ], 
        "stateMutability": "nonpayable", 
        "type": "function"
    }
]

