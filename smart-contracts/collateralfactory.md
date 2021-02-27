# CollateralFactory.sol



```text
function setCollateralizationRatio(uint256 ratio)
```



```text
function setIssueFeeRate(uint256 _issueFeeRate)
```



```text
function setMinLoanCollateralSize(uint256 _minLoanCollateralSize)
```



```text
function setAccountLoanLimit(uint256 _loanLimit)
```



```text
function setLiquidationRatio(uint256 _liquidationRatio)
```



```text
function getContractInfo()
```



```text
function issuanceRatio()
```



```text
function loanAmountFromCollateral(uint256 collateralAmount)
```



```text
function collateralAmountForLoan(uint256 loanAmount)
```



```text
function getMintingFee(address _account, uint256 _loanID)
```



```text
function calculateAmountToLiquidate(uint debtBalance, uint collateral)
```



```text
function openLoanIDsByAccount(address _account)
```



```text
function getLoan(address _account, uint256 _loanID)
```



```text
function getLoanCollateralRatio(address _account, uint256 _loanID)
```



```text
function _loanCollateralRatio(SynthLoanStruct memory _loan)
```



```text
function openLoan(uint256 _loanAmount)
```



```text
function closeLoan(uint256 loanID)
```



```text
function depositCollateral(address account, uint256 loanID)
```



```text
function withdrawCollateral(uint256 loanID, uint256 withdrawAmount)
```



```text
function repayLoan(
    address _loanCreatorsAddress,
    uint256 _loanID,
    uint256 _repayAmount
)
```



```text
function liquidateLoan(
    address _loanCreatorsAddress,
    uint256 _loanID,
    uint256 _debtToCover
)
```



```text
function _closeLoan(
    address account,
    uint256 loanID,
    bool liquidation
)
```



```text
function _getLoanFromStorage(address account, uint256 loanID)
```



```text
function _updateLoan(
    SynthLoanStruct memory _synthLoan,
    uint256 _newLoanAmount
)
```



```text
function _updateLoanCollateral(SynthLoanStruct memory _synthLoan, uint256 _newCollateralAmount)
```



```text
function _recordLoanClosure(SynthLoanStruct memory synthLoan)
```



```text
function _incrementTotalLoansCounter()
```



```text
function _calculateMintingFee(uint256 _ethAmount)
```



```text
function _checkLoanIsOpen(SynthLoanStruct memory _synthLoan)
```



```text
function syntharb()
```

