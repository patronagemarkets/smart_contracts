## Harberger Collectibles Smart Contracts

This is a smart contract platform for the deployment of scalable Harberger Collectibles on Ethereum. It's an extension of "This Artwork Is Always On Sale". (https://github.com/simondlr/thisartworkisalwaysonsale)

### Contracts

This is a work-in-progress.

The contracts consists of three components:

1) A global HarbergerSteward, responsible for collecting deposits and foreclosing ERC721. Forked from OpenZeppelin implementation.
2) ERC721 alongside a fixedOperator extension.
3) A Cheap Proxy Factory to readily deploy/mint Harberger Collectible ERC721 contracts.

### Front-end

The front-end is a modified version of 'This Artwork Is Always On Sale' with a routable interface to a deployed Harberger Collectible. The front-end checks if the contract interface complies with the standards and then displays the necessary information.

A demo is incoming.

### Testing

`npm run chain`  
then
`truffle test`

The Gas Reporter is disabled (since it is slower). Enable gas reporter in truffle config to check.

The test may sometimes fail due to split-second changes in when the test is run due to patronage incrementing per second.
Just re-run.

NOTE: It costs ~$0.12 tx fee at 5 gwei gas price & 133 usd/eth to buy. 

### Running

After installing packages, main directory:

`npm run chain`  
or  
`npm run moving_chain`  

This creates a local ganache-cli instance. The latter includes auto-mining of blocks to showcase the patronage owed increasing on the front-end.

`truffle migrate`

This deploys the ERC721-artwork/nft & the ArtSteward.

`cd app`  
`npm run start`  

### Patronage As An Asset Class

This concept is based this blog post: https://blog.simondlr.com/patronage-as-an-asset-class. To create Patronage as an asset class.

### Thanks

The initial Steward code was inspired by code from Billy Rennekamp: https://github.com/okwme/harberger-ads-contracts & Todd Proebsting: https://programtheblockchain.com/posts/2018/09/19/implementing-harberger-tax-deeds/.

### License

Code License:
MIT