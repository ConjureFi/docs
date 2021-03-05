# ConjureFactory.sol

### Asset Creation Functions

### `init`

```text
    function init(
        uint256 mintingFee_,
        uint8 assetType_,
        // pack variables together because of otherwise stack too depp error
        uint256[2] memory divisorRatio_,
        bool inverse_,
        address[] memory oracleAddresses_,
        uint8[] memory oracleTypes_,
        string[] memory signatures_,
        bytes[] memory calldata_,
        uint256[] memory values_,
        uint256[] memory weights_,
        uint256[] memory decimals_
    ) public
```

Initializes the Conjure Asset with mintingFee, the asset Type, and all the oracle-related data.

It also sets the divisor and the C-Ratio for the later generated collateral system.

Aslo there is on indicator which can set the price logic to be inverse.

This function also mints a new instance of the CollateralFactory for the synth and triggers the initial price calculation via getPrice\(\). The array sizes must have equal lengths.

### `getPriced`

```text
function getPrice()
```

Capsules the price logic. Calls the internal price function and checks if the price is an inverse price.

If inverse the logic will be  

`price = _deploymentPrice - (currentPrice - _deploymentPrice)`

Also, set the last observed price and timestamp for that. If an asset price is equal or below 0 then it will trigger the close of the assets collateral system \(no more loan openings\)

### `getPriceInternal`

```text
function getPriceInternal()
```

This function calculates the price in regard to the asset type and all the different oracle types.

The price is calculated as follows:

Check each oracle type on its own \(Chainlink, Uniswap, and custom oracle\)

Check the asset type \(Single, Basket, Index, or Sqrt Index\)

Get the oracle feeds price and norm it in case of mismatching decimals.

Calculate either median price \(single asset\), weighted average price \(basket asset\), or marketcap, sqrt market cap, and divide by the indexdivisor provided.

### `setEthUsdChainlinkOracle`

```text
function setEthUsdChainlinkOracle(address neworacle)
```

This function allows setting a new Chainlink price feed oracle for the ETH/USD price Conjure uses.

Only allowed by the contract owner.

### `setUniswapOracle`

```text
function setUniswapOracle(address newunioracle)
```

It is possible to set a new Uniswap Oracle to use. 

Only allowed by the contract owner.

### `burn`

```text
function burn(address account, uint amount)
```

Interface method to burn synths and can only be called by the Collateral contract instance.

### `mint`

```text
function mint(address account, uint amount)
```

Interface method to mint synths and can only be called by the Collateral contract instance.

### `_internalIssue`

```text
function _internalIssue(address account, uint amount)
```

The internal method is called by mint. This function mints the actual Conjure synths.

### `_internalBurn`

```text
function _internalBurn(address account, uint amount)
```

The internal method is called by burn. This function burns the actual Conjure synths.

### `changeOwner`

```text
function changeOwner(address payable _newOwner)
```

Change owner of the Conjure contract, only callable by the current owner.

### `collectFees`

```text
function collectFees()
```

This function lets the owner collect all the fees generated from users minting new synths. This will transfer the contract's ether balance to the owner.

### `getLatestPrice`

```text
function getLatestPrice(AggregatorV3Interface priceFeed)
```

This function calls the getLatestPrice of an AggregatorV3Interface of Chainlink. Used to determine the latest price of a Chainlink Price Feed. 

### `getLatestETHUSDPrice`

```text
function getLatestETHUSDPrice()
```

Always returns the latest ETH/USD price from the used Chainlink price feed. 

### `quickSort`

```text
function quickSort(uint[] memory arr, int left, int right)
```

Function to sort an array.

### `getAverage`

```text
function getAverage(uint[] memory arr)
```

Function to return the average value of a given array.

### `sort`

```text
function sort(uint[] memory data)
```

Calls the quicksort function.

### `sqrt`

```text
function sqrt(uint256 y)
```

Returns the square root of a number.

### `getLatestPrice`

```text
function getLatestPrice()
```

This function always returns the latest price which is recorded in the contract for a given synth. 

### `ConjureMint`

```text
function ConjureMint(
    string memory name_,
    string memory symbol_,
    address payable owner_,
    address uniswapv2oracle_,
    address collateralfactory_
)
```

This is the mint new contract function of the ConjureFactory contract. This will mint a new Conjure contract. 

Will take the name, symbol, owner, and the addresses of the Uniswap oracle and the collateralfactory as an argument. And will set the new contract up, so it can be initialized in the next step.

### `newFactoryOwner`

```text
function newFactoryOwner(address payable newOwner)
```

Function to change the current factory owner. Only available for the current factory owner.

### `getFactoryOwner`

```text
function getFactoryOwner()
```

Interface method to get the current factory owner. Used by the Collateral Contract to determine which address the cut of the fees has to be sent to.

