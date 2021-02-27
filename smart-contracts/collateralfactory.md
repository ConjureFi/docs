# CollateralFactory.sol

### `setCollateralizationRatio`

```text
function setCollateralizationRatio(uint256 ratio)
```

Lets a user set a custom collateralization value between 100% and 1000%.

### `setIssueFeeRate`

```text
function setIssueFeeRate(uint256 _issueFeeRate)
```

This function lets a user set the Minting Fee. Values from 0 up to 2.5% are accepted.

### `setMinLoanCollateralSize`

```text
function setMinLoanCollateralSize(uint256 _minLoanCollateralSize)
```

Lets a user set a custom loan collateral size of their contract.

### `setAccountLoanLimit`

```text
function setAccountLoanLimit(uint256 _loanLimit)
```

This function lets the contract creator set a custom account loan limit. Should not excess 1000.

### `setLiquidationRatio`

```text
function setLiquidationRatio(uint256 _liquidationRatio)
```

Sets a custom liquidation ratio which has to be higher than 100%. Preset at 120%

### `getContractInfo`

```text
function getContractInfo()
```

Returns all configuration variables of the contract.

```text
_collateralizationRatio,
_issuanceRatio,
_issueFeeRate,
_minLoanCollateralSize,
_totalIssuedSynths,
_totalLoansCreated,
_totalOpenLoanCount,
_ethBalance
```

### `issuanceRatio`

```text
function issuanceRatio()
```

Returns the value of 100 / collateralization ratio.

### `loanAmountFromCollateral`

```text
function loanAmountFromCollateral(uint256 collateralAmount)
```

Returns the maximum loan amount which can be taken given a certain collateral amount. Calculated by the collateralAmount \* issuanceRatio \* price of the Asset / current ETH Price.

### `collateralAmountForLoan`

```text
function collateralAmountForLoan(uint256 loanAmount)
```

Calculates the amount of collateral needed for a given loan amount. Calculated by the loanAmount \* \(collateralization ratio / current ETH Price \* current Asset Price\)

### `getMintingFee`

```text
function getMintingFee(address _account, uint256 _loanID)
```

Gets the minting fee of a given loan.

### `calculateAmountToLiquidate`

```text
function calculateAmountToLiquidate(uint debtBalance, uint collateral)
```

Calculates the amount to liquidate given a debtBalance and a collateral amount. This will return the amount of synth which can be liquidated in order to fix the C-Ratio of a loan. Returns higher amounts if the C-Ratio drops below 100 + liquidation penalty \(10% in the Conjure Protocol\)

```text
/**
 * r = target issuance ratio
 * D = debt balance
 * V = Collateral
 * P = liquidation penalty
 * Calculates amount of synths = (D - V * r) / (1 - (1 + P) * r)
 */
```

### `openLoanIDsByAccount`

```text
function openLoanIDsByAccount(address _account)
```

Returns all open loans in the system given an address.

### `getLoan`

```text
function getLoan(address _account, uint256 _loanID)
```

Returns detailed information about a loan given the account address and the loan id. Returns the following details:

```text
account
collateralAmount
loanAmount
timeCreated
loanID
timeClosed
totalFees
```

### `getLoanCollateralRatio`

```text
function getLoanCollateralRatio(address _account, uint256 _loanID)
```

### `_loanCollateralRatio`

```text
function _loanCollateralRatio(SynthLoanStruct memory _loan)
```

### `openLoan`

```text
function openLoan(uint256 _loanAmount)
```

### `closeLoan`

```text
function closeLoan(uint256 loanID)
```

### `depositCollateral`

```text
function depositCollateral(address account, uint256 loanID)
```

### `withdrawCollateral`

```text
function withdrawCollateral(uint256 loanID, uint256 withdrawAmount)
```

### `repayLoan`

```text
function repayLoan(
    address _loanCreatorsAddress,
    uint256 _loanID,
    uint256 _repayAmount
)
```

### `liquidateLoan`

```text
function liquidateLoan(
    address _loanCreatorsAddress,
    uint256 _loanID,
    uint256 _debtToCover
)
```

### `_closeLoan`

```text
function _closeLoan(
    address account,
    uint256 loanID,
    bool liquidation
)
```

### `_getLoanFromStorage`

```text
function _getLoanFromStorage(address account, uint256 loanID)
```

### `_updateLoan`

```text
function _updateLoan(
    SynthLoanStruct memory _synthLoan,
    uint256 _newLoanAmount
)
```

### `_updateLoanCollateral`

```text
function _updateLoanCollateral(SynthLoanStruct memory _synthLoan, uint256 _newCollateralAmount)
```

### `_recordLoanClosure`

```text
function _recordLoanClosure(SynthLoanStruct memory synthLoan)
```

### `_incrementTotalLoansCounter`

```text
function _incrementTotalLoansCounter()
```

### `_calculateMintingfee`

```text
function _calculateMintingFee(uint256 _ethAmount)
```

### `_checkLoanIsOpen`

```text
function _checkLoanIsOpen(SynthLoanStruct memory _synthLoan)
```

### `syntharb`

```text
function syntharb()
```

