# Ground-Zero-
Overview of implementation into Ground Zero 
geth \
  --http --http.addr 0.0.0.0 --http.port 8545 \
  --http.api eth,net,web3 \
  --networkid 1234

  import { Web3 } from "web3";

// simplest: pass URL as provider
const web3 = new Web3("http://localhost:8545");

// test connectivity
const blockNumber = await web3.eth.getBlockNumber();
console.log("Ground Zero block:", blockNumber);

import { Web3, HttpProvider, WebSocketProvider } from "web3";

const httpProvider = new HttpProvider("http://localhost:8545");
const web3Http = new Web3(httpProvider);

const wsProvider = new WebSocketProvider("ws://localhost:8546");
const web3Ws = new Web3(wsProvider);

import { JsonRpcProvider } from "ethers";

const provider = new JsonRpcProvider("http://localhost:8545", {
  chainId: 1234,
  name: "ground-zero",
});

// sanity check
console.log("Ground Zero block:", await provider.getBlockNumber());

from web3 import Web3

w3 = Web3(Web3.HTTPProvider("http://localhost:8545"))
print("Connected:", w3.is_connected())
print("Ground Zero block:", w3.eth.block_number)
