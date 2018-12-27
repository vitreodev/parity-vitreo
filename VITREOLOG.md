## Parity-Viteo

Port parity-ethereum to parity-vitreo

The full list of changes:
1.  Add parity-vitreo configuration file `config.toml` at `parity-vitreo/config.toml`.
2.  Add parity-vitreo chain specification file at `vitreo.json` `/parity-vitreo/ethcore/res/ethereum/vitreo.json`.
3.  Create a new Vitreo mainnet chain specification lookup function at `/parity-vitreo_00/ethcore/src/ethereum/mod.r:45` 
4.  