# nsm.shieldedlabs.net

One static page that shows the Zcash NSM Value Balance (ZIP 237) at the chain tip.

## How it works

1. The page reads the tip height and the tip block's chain value pools from the Blockchair API.
2. It computes scheduled issuance up to the tip (ZIP 218 subsidy from NU7 onward).
3. NSM balance = scheduled issuance minus the sum of the chain value pools.

At NU7 activation (block 3,543,405) this formula gives the ZIP 237 seed, 368.58445520 ZEC, to the zatoshi.
Each block after that adds 60% of its fees (ZIP 235).

The page stops with an error from the reissuance height (block 8,939,664). Reissuance needs the NSM balance of every prior block, so the formula changes there.

## Deploy

GitHub Pages serves `main` from the repo root. DNS: `nsm.shieldedlabs.net` CNAME `shieldedlabs.github.io`.
