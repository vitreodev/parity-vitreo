## Parity-Viteo

Port parity-ethereum to parity-vitreo

The full list of changes:
1.  Added parity-vitreo configuration file `config.toml` at `parity-vitreo/config.toml`.
2.  Added parity-vitreo chain specification file at `vitreo.json` `/parity-vitreo/ethcore/res/ethereum/vitreo.json`.
3.  Added Vitreo mainnet chain specification public function at `/parity-vitreo_00/ethcore/src/ethereum/mod.r:45` 
4.  Added Vitreo mainnet paramaters to `/parity/params.rs: 34, 56, 65, 91, 117, 