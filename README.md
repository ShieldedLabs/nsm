# nsm.shieldedlabs.net

One static page that shows the Zcash NSM Value Balance (ZIP 237) at the chain tip.
It uses the shieldedlabs.net style: tokens, fonts, wordmark and icons come from ShieldedLabs/website (fonts under the SIL OFL, licenses in `fonts/`).

## How it works

The page reads the tip height and the NSM Value Balance from the zecblock API (`/v1/network/accounting`, field `nsmBalanceZat`, from the node's `getblockchaininfo.nsmValueBalanceZat`).
The ZIP 237 seed at NU7 activation (block 3,543,405) is 368.58445520 ZEC. Each block after that adds 60% of its fees (ZIP 235).

The page stops with an error from the reissuance height (block 8,939,664), because "Removed since NU7" stops being balance minus seed there.

## Deploy

GitHub Pages serves `main` from the repo root. DNS: `nsm.shieldedlabs.net` CNAME `shieldedlabs.github.io`.
