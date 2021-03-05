# Collateral System

## Summary

In Conjure minting a Synth is technically opening a Collateralized Dept Position \(CDP\) working as a loan. If a user wishes to mint a synth they have to come up with a deposit in Ether to create the underlying collateralization.

## Loans

All synths have to be minted. In order to create value and establish an underlying value for a minted asset, the user has to provide a certain amount of ETH as collateral in order to take the loan.

When opening a loan Conjure aims for a 120% collateral ratio. On the loan tab, a user can see exactly how much ETH they have to deposit in order to get to a certain C-Ratio.

After the loan is taken out the specified amount is then minted to the user's wallet and the ETH is transferred into the smart contract where the loan collateral is being held.

If a user wants to get their collateral back they have the option to close the loan. Therefore, they will have to hold the number of synths minted by the loan in their wallet. The synths are then being burnt and the collateral gets unlocked and sent back to the borrower.

It is also possible to withdraw parts of the collateral. This will affect the C-Ratio and a user cant withdraw ETH that will make them fall under the desired ratio of 120%.

## Collateral

The collateral acts as the underlying value of each loan and is deposited as ETH. In Conjure the system is set to keep a 120% C-Ratio overall loans. If the ratio of a user loan drops below 120% the loan is suspect to liquidation.

It is the borrowers' responsibility to keep the collateralization level above. If the value of the collateral drops or the value of the asset increases the user has the option to either deposit more ETH as collateral into the loan or also to repay parts of the loan \(burn some of their synths\) to fix their C-Ratio and don't get into the risk of liquidation.

## Liquidations

If the collateralization ratio drops below 120% a loan is at risk of liquidation. Any address can then liquidate or partially liquidate the loan.

If an address wants to liquidate a loan at risk, they have to cover parts of their debt in the form of the synth.

The amount to be liquidated is calculated as follows:

* V = Value of ETH Collateral in USD
* D = Value of the Synth in USD
* t = Liquidation Ratio
* S = Amount of USD debt to liquidate
* P = Liquidation Penalty %

$$
S = (t* D -V) / ( t- (1+P))
$$

On top of the liquidation amount, the liquidator will also get awarded a liquidation penalty of 10%. This amount is taken directly from the borrowers collateral.

