# IEtherCollateral

The IEtherCollateral interface allows the Conjure Contract to stop the new issuance of loans and also new ETH deposits to current open loans if the price of an asset reaches 0.

```text
// SPDX-License-Identifier: MIT
pragma solidity ^0.6.0;

/// @author Conjure Finance Team
/// @title IEtherCollateral
/// @notice Interface for interacting with the EtherCollateral Contract
interface IEtherCollateral {

    /**
     * @dev Sets the assetClosed indicator if loan opening is allowed or not
     * Called by the Conjure contract if the asset price reaches 0.
     *
    */
    function setAssetClosed() external;
}
```

