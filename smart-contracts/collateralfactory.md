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

### `getContractInfo`

```text
function getContractInfo()
```

### `issuanceRatio`

```text
function issuanceRatio()
```

### `loanAmountFromCollateral`

```text
function loanAmountFromCollateral(uint256 collateralAmount)
```

### `collateralAmountForLoan`

```text
function collateralAmountForLoan(uint256 loanAmount)
```

### `getMintingFee`

```text
function getMintingFee(address _account, uint256 _loanID)
```

### `calculateAmountToLiquidate`

```text
function calculateAmountToLiquidate(uint debtBalance, uint collateral)
```

### `openLoanIDsByAccount`

```text
function openLoanIDsByAccount(address _account)
```

### `getLoan`

```text
function getLoan(address _account, uint256 _loanID)
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

