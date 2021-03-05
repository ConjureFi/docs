# Conjure Assets

## Summary

Conjure lets you allows for user-created synthetic assets based on various oracle price feeds. A user can set up their own arbitrary asset with just 2 transactions, all simplified with a simple User Interface.

## Creation

To start the creation process, a user has to simply put in the name and symbol of the asset they want to create.

This brings up the first transaction in which a brand-new Instance of a Conjure contract is minted. \(The call triggers the [ConjureFactory.sol](../smart-contracts/conjurefactory.sol.md)\). The oracles and type will be set as the 2nd transaction.

## Initialization

After the first transaction, the instance of the Conjure contract is now ready to be set up.

The user will be presented the following options when they set up their asset:

### Asset Type

Here the user chooses the asset type of the synth to be minted. This reflects in the price calculation later on. The following asset types are available:

**Single Asset**

This asset takes the median price from all the given price from the oracles. This is useful if the use case is to hedge against an oracle provider going down or to interpolate the price from price sources going off.

**Basket Asset**

This type allows users to create their very own asset based on the given price oracles. The price will be the weighted average price of all the sources. Weights can be given for each source.

**Index Market Cap**

This asset type allows creating indices by market cap calculation. The contract will look up the ERC20 address, gathers the totalsupply\(\) and also the price from uniswap, and calculates the market cap from it. It also takes advantage of the divisor which can be specified to create any price they want to by managing the final price to a more managable and user friendly amount.

**Index Sqrt Market Cap**

This asset type allows creating indexes by market cap calculation. The contract will look up the ERC20 address, gathers the totalsupply\(\) and also the price from uniswap, and calculates the square root _\*\*_market cap from it. It also takes advantage of the divisor which can be specified to create any price they want to by managing the final price to a more managable and user friendly amount.

### Minting Fee

Users can specify a minting fee of up to 2.5%. This fee is later calculated on top of the loan collateral a user has to pay to open a loan. 75% of the minting fee goes directly to the asset creator and 25% is taken as a fixed platform fee \(Conjure takes 0% at a 0% fee\) sent to the DAO address.

### Oracle Types

**Chainlink**

Here a user can select from a dropdown. There are all currently available chainlink price feeds to select \(in USD nomination\)

**Uniswap**

Here a user can supply an ERC20 token address and an Uniswap Oracle will calculate the TWAP price for the token. The token must be registered with the oracle contract and have a price history.

**Custom**

If there is no template available for the price it is possible to send custom call data to any contract needed in order to retrieve a price.

**Conjure**

Finally, it is also possible to supply an already existing Conjure address as a price feed. The contract will then look it up in the internal system and takes the price from the arbitrary asset.

## Price Finding

The prices are either median or weighted average prices. For the index asset types, we use market cap or square root market cap.

Inverse Assets

If the inverse boolean flag is set to true the price will increase if the tracked assets price decreases and vice versa. It follows this logic:

`price = _deploymentPrice - (currentPrice - _deploymentPrice)`

