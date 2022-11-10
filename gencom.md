# Gencom

Gencom ([https://gencom-shiden.vercel.app/](https://gencom-shiden.vercel.app/)) provides a gamified way to create and own NFTs. The users compete and/or collaborate in a decentralized and permissionless manner to create pixelated art where each pixel represents a fractional nft of the overall artwork.  
Users bid on the pixels to gain ownership, allowing them to color that pixel. The bid amount goes to the last owner of that pixel. Thus in this way, each participant earns a profit from the sale and/or gets to own the fractional nft, which is a benefit of our Play-to-Earn (P2E) model.  
Usually, the NFTs obtained from the P2E games start losing their value once the game ends. To overcome this issue, We came up with a novel approach of having a dynamic state in our NFTs which opens up the possibility of a secondary market.  

We have developed this application using ink! smart contract, polkadot.js library and React.

## Astar Bounty

[WebAssembly dApps](https://github.com/AstarNetwork/AstarBounties/issues/15)

## Description

Gencom provides an innovative way for users to collaboratively create digital artwork and own pieces of it as NFTs. The artwork is created on a 32x32 grid (aka canvas) and the whole process is divided into three stages:

### Creation phase

A user can create a new canvas by paying a small fee which goes to the developers. The creator needs to specify the following parameters:

* _Title:_ It is the heading of the canvas

* _Description:_ A brief information about this canvas

* _Base Price:_ It is the minimum price of each pixel the first bidder needs to pay to gain its ownership.

* _Premium Percentage:_ It is the percentage surplus of the last bid price of a given pixel, which a user needs to pay to capture it from its current owner.

* _Start Time:_ The start time of the bidding phase

* _End Time:_ The end time of the bidding phase

* _Is Dynamic:_ If enabled, the pixel owners can change the pixel colors even after the bidding phase. 

> All the information can be updated prior to the start of the bidding phase

### Bidding phase

During this period, Users bid on the pixels to gain ownership, allowing them to color that pixel. If a pixel doesn’t have any current owner, a user can pay the base price (or more) to become the first owner of that pixel otherwise they must bid at least the sum of the current pixel price plus the premium percentage amount to become the new owner of that pixel. A commission fee is deducted from the bid amount and the rest is transferred to the previous owner (or to the creator in case it was the first bid of that pixel). In this way, Every time a bid is placed successfully, the previous owner/creator of that pixel earns a profit.

This method of bidding on the pixels (NFT) helps with the price discovery of the artwork.

### Post phase

The individual pixels collectively form an NFT artwork and therefore pixel owners have fractional ownership of the art. If the canvas creator had enabled dynamic NFT, then owners can still change the color of the pixels they own even after the bidding phase. Having such a feature enables the NFTs to appreciate/retain their value in the secondary market since the NFTs can be purchased to modify the artwork and it evolves over time.

## Novelty/Originality
  
* Gencom introduces the idea of collaborative art - Users can create digital artwork together in a decentralised and permissionless manner.

* Gencom uses the novel idea of fractionalizing the digital asset (artwork) into multiple NFTs.

* Gencom integrates the idea of Dynamic NFT, where the state of digital assets represented by the NFT can be changed even after minting.

## Technical complexity

### Smart Contract

A lot of design considerations had to be made because of the current restrictions in the ink! language. Events are not supported when using cross-contract calls so we had to write everything in a single contract which made the implementation a bit complex. Also, we couldn’t club related variables in a struct that were frequently updated as that would rewrite the whole struct again in the storage even for small changes, so we again had to create an independent mapping for each such variable. This in turn increased the get/update cost when those variables had to be read/inserted together. The contract was going way over the gas limit on the public networks for some crucial actions and in other cases, we were exceeding the buffer capacity. We had to try many different implementations until we found a sweet spot that worked. This was a big relief as we had started to believe that it was not yet possible to implement such complex dApps in ink!

### Frontend

In the frontend, we have developed a beautiful aesthetic UI using react and MUI. We didn’t want to use a backend so we had to optimally handle states to minimize rerendering. And we rendered the grid using SVG since it is lightweight and helped us in achieving a low-latency rendering. The initial iteration of our interface had a load time of 15+ seconds, which was reduced to < 1 second.

### Integration

The major issue was the lack of proper documentation of the polkadot-api library and the confusing output format returned by the API calls. We had to check the contract methods return type to decide where to read the response/error from, in some cases, we get it from the output field, and in the rest from the result field.

## Daily/mass usability

NFTs are the best channel for crypto adoption for mass audiences. Such gamification of NFT generation and ownership will attract more users to the chain. Dynamic NFTs (aka Evolving NFTs) would be the new trend in the NFT space and allow for more innovation.

## Impact of project

* Our project is one of the early adopters of ink! smart contract and polkadot.js tech stack. It will act as a great source of reference for future builders and projects utilizing the given tech stack.

* We believe our project could be the one to popularize the concept of dynamic NFTs in the mainstream.

* We believe our unique and innovative project will help in developing the NFT space in the polkadot ecosystem. 

## Future work
* **Invite-only rooms:** it’ll allow only the invited users to participate in the bidding process.

* **Batch bidding feature:** it will help users to bid on multiple pixels in a single transaction, thus making the bidding process smoother and effortless.

* We plan to leverage the **subsocial platform** to provide a communication channel for better collaboration.

* Incorporate the following features in frontend:

    * Better visibility of high-traffic rooms in the trending section.
    * Increase the color options in the color palette.
    * Search and sort feature for finding relevant rooms.

    and many more…

* We plan to integrate with NFT marketplaces to facilitate the buying and selling of Gencom NFTs on secondary markets.

* Extend the support to **ERC1155** and **PSP34** standards.

## Tech Stack

* Ink! smart contract
* PolkadotJS library
* React
* MUI (Material UI)

## Deployment 

Link : [https://gencom-shiden.vercel.app/](https://gencom-shiden.vercel.app/)

## Pitch Video

Link: [Video](https://www.youtube.com/watch?v=uMZEPvLVcAo)

## Github Link

Link: [Gencom-shiden | Github](https://github.com/SayanKar/gencom-nft/tree/shiden-network)

## Team Members

1. Nimish Agrawal - realnimish@gmail.com

2. Sayan Kar - sayankar1308@gmail.com

3. Soumyajit Deb - debsoumyajit100@gmail.com
