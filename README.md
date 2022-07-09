# Disperse DAPP Build Using Ink! and React

Disperse DAPP is a batching protocol for both native currency and PSP22/ERC20 or equivalent tokens that can help reduce gas cost and reduces time/complexity for multiple transfers by batching them in a single block. The Dapp contract is written completely in ink! and makes use of OpenBrush's PSP22 protocol. The front-end is programmed in react/javascript. Polkadot.js wallet is the minimum requirement to use this app. Rust toolchain and substrate-contracts-node are a must for the local backend testing and development. Node.js and yarn will be need for the local deployment of the frontend. 

### Documentation

This DAPP is based on Artem K's [disperse app on ethereum. (PDF Link)](https://disperse.app/disperse.pdf)


To batch together native currency.

```pub fn disperse_currency(&mut self, addresses: Vec<AccountId>, values: Vec<Balance>)-> Result<(),Error>  ```

addresses is an array of addresses and the values is the array of amount that is being send to each of the addresses respectively.

To batch together PSP22/ERC20 or equivalent tokens.

```pub fn disperse_token(&mut self,token_address: AccountId, addresses: Vec<AccountId>, values: Vec<Balance>)-> Result<(),Error>```

token_address is the contract address of the PSP2220 contract. The other values are same as above.

## Contact Information

rafat.hsn@gmail.com

## Name of Bounty : Front-end, tools, or utility service

## Project Information


DAPP is live at https://famous-llama-2bd8e8.netlify.app

Slides : https://docs.google.com/presentation/d/1iMBasWGsGutQSdDwc1XhFPmtathxhBF25aJJAfUU9KI/edit?usp=sharing

Contract Address : ```XAPTQfpsddWDJ9kkkVBQjkchzHjpD9Bz4noneJmfBvTySC7``` [on Shibuya Testnet]

## Demo Video


## License : MIT



