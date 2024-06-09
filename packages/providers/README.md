## Arbitrum `eth_getTransactionByHash` hotfix

Issue can be described [here](https://github.com/OffchainLabs/nitro/pull/2336).

The modifications affect `@ethersproject/providers`. The forked packaged is named `ethersproject-providers-arbitrum-hotfix`.

Currently the latest version is `ethersproject-providers-arbitrum-hotfix@5.7.7`.

To use this hotfix, use this yarn resolution in your `package.json`
```
"resolutions": {
        "@ethersproject/providers": "npm:ethersproject-providers-arbitrum-hotfix@5.7.7"
    }
```

The hotfix is to add `300ms` delay to  the `getTransaction/eth_getTransactionByHash` call. A cached `chainID` has been added to check for Arbitrum chain ID (42161), and initiate the delay if this matches.