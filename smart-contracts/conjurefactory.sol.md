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





```text
function setUniswapOracle(address newunioracle)
```





```text
function burn(address account, uint amount)
```





```text
function mint(address account, uint amount)
```





```text
function _internalIssue(address account, uint amount)
```





```text
function _internalBurn(address account, uint amount)
```





```text
function changeOwner(address payable _newOwner)
```





```text
function collectFees()
```





```text
function getLatestPrice(AggregatorV3Interface priceFeed)
```





```text
function getLatestETHUSDPrice()
```





```text
function quickSort(uint[] memory arr, int left, int right)
```





```text
function getAverage(uint[] memory arr)
```





```text
function sort(uint[] memory data)
```





```text
function sqrt(uint256 y)
```





```text
function getLatestPrice()
```





```text
function ConjureMint(
    string memory name_,
    string memory symbol_,
    address payable owner_,
    address uniswapv2oracle_,
    address collateralfactory_
)
```





```text
function newFactoryOwner(address payable newOwner)
```





```text
function getFactoryOwner()
```

