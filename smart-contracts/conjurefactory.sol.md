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

Initializes the Conjure Asset with mintingFee, the asset Type and all the oracle related data.

### `getPrice`

```text
function getPrice()
```

This function calculates the price in regard to the asset type and all the different oracle types.

