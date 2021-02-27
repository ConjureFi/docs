# ConjureFactory.sol

### Asset Creation Functions

> ### `configure`

```text
    function init(
        uint256 mintingFee_,
        uint8 assetType_,
        uint256 indexdivisor_,
        address[] memory oracleAddresses_,
        uint8[] memory oracleTypes_,
        string[] memory signatures_,
        bytes[] memory calldata_,
        uint256[] memory values_,
        uint256[] memory weights_,
        uint256[] memory decimals_
    )
```

Initializes the Conjure Asset with mintingFee, the asset Type, and all the oracle-related data.

This function also mints a new instance of the CollateralFactory for the synth and triggers the initial price calculation via getPrice\(\).

### `getPrice`

```text
function getPrice()
```

This function calculates the price in regard to the asset type and all the different oracle types.



### `setEthUsdChainlinkOracle`

```text
function setEthUsdChainlinkOracle(address neworacle)
```





### `setUniswapOracle`

```text
function setUniswapOracle(address newunioracle)
```



### `burn`

```text
function burn(address account, uint amount)
```



### `mint`

```text
function mint(address account, uint amount)
```



### `_internalIssue`

```text
function _internalIssue(address account, uint amount)
```



### `_internalBurn`

```text
function _internalBurn(address account, uint amount)
```



### `changeOwner`

```text
function changeOwner(address payable _newOwner)
```



### `collectFees`

```text
function collectFees()
```



### `getLatestPrice`

```text
function getLatestPrice(AggregatorV3Interface priceFeed)
```



### `getLatestETHUSDPrice`

```text
function getLatestETHUSDPrice()
```



### `quickSort`

```text
function quickSort(uint[] memory arr, int left, int right)
```



### `getAverage`

```text
function getAverage(uint[] memory arr)
```



### `sort`

```text
function sort(uint[] memory data)
```



### `sqrt`

```text
function sqrt(uint256 y)
```



### `getLatestPrice`

```text
function getLatestPrice()
```



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



### `newFactoryOwner`

```text
function newFactoryOwner(address payable newOwner)
```



### `getFactoryOwner`

```text
function getFactoryOwner()
```

