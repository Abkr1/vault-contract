# Vault — 0xf3bCeDaB2998933c6AAD1cB31430D8bAb329dD8C

Extracted verified source for the **Alongside AMKT `Vault`** contract on **Ethereum mainnet**.

- **Address:** [`0xf3bCeDaB2998933c6AAD1cB31430D8bAb329dD8C`](https://etherscan.io/address/0xf3bCeDaB2998933c6AAD1cB31430D8bAb329dD8C)
- **Chain ID:** 1 (Ethereum mainnet)
- **Contract name:** `Vault` (`src/Vault.sol`)
- **Compiler:** Solidity `0.8.18+commit.87f61d96`, optimizer enabled (200 runs), EVM `paris`
- **Verification:** exact match on Etherscan / Sourcify
- **Deployer:** [Alongside: Deployer `0x91F23057Ee6e2d1E1BA00A7c1D71Ba1a0B2c3113`](https://etherscan.io/address/0x91F23057Ee6e2d1E1BA00A7c1D71Ba1a0B2c3113) (creation tx `0x7156d051b09a7b0ed91a6e695fa2786e37aa30f794d9111abe338fb4bd38edba)
- **Source of this repo:** Sourcify v2 API (`stdJsonInput` + `abi`), vendored under `src/` and `lib/`

This repo is a mirror for reading / auditing / reuse. It is **not** the upstream Alongside repo and is not deployed by this repo.

## Layout

```
vault-contract/
  src/
    Vault.sol              # main contract (Ownable2Step + IVault)
    Common.sol
    lib/VArray.sol
    lib/FixedPoint.sol
    interfaces/IVault.sol
    interfaces/IIndexToken.sol
  lib/
    openzeppelin-contracts/            # vendored OZ used by the verified build
    openzeppelin-contracts-upgradeable/
  abi.json                 # contract ABI from Sourcify
  foundry.toml             # solc 0.8.18, optimizer 200 runs, evm paris
  remappings.txt
```

Constructor:

```solidity
constructor(
  IIndexToken _indexToken,
  address _owner,
  address _feeRecipient,
  address _emergencyResponder,
  uint256 _inflationRate
)
```

## Build

Requires [Foundry](https://book.getfoundry.sh/).

```shell
forge build
```

Expected: compiles `src/Vault.sol` with solc 0.8.18.

## Test

No tests are vendored (the verified bundle contains only deployment sources). Add your own under `test/`:

```shell
forge test
```

## License

- `src/Vault.sol` and Alongside sources: `SPDX-License-Identifier: GPL-3.0` (as in the verified source, preserved per file).
- OpenZeppelin files under `lib/`: their original SPDX headers (MIT) apply.
- No new license grant is made by this mirror; check the upstream Alongside project for terms.
