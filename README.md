# DSP Whitelist

This contract is to store and manage account whitelising for DSPs.

## Quickstart

```
./build.sh
./deploy.sh
./test.sh
```

## [Releases](https://github.com/EOS-Nation/dsp-whitelist/releases)

- [`dspwhitelist.wasm`](https://github.com/EOS-Nation/dsp-whitelist/releases/download/1.0.0/dspwhitelist.wasm) (v1.0.0)
- [`dspwhitelist.abi`](https://github.com/EOS-Nation/dsp-whitelist/releases/download/1.0.0/dspwhitelist.abi) (v1.0.0)

## ACTIONS

- [`add`](#action-add)
- [`remove`](#action-remove)
- [`checklist`](#action-checklist)

## TABLES

- [`whitelist`](#table-whitelist)

### ACTION `add`

Adds user to whitelist table

### params

- `@param {name} account` - EOSIO account name to whitelist
- `@param {name} service` - DSP service
- `@param {name} package` - DSP package name

### example

```bash
cleos push action <DSP> add '["myaccount","ipfsservic1","package1"]' -p <DSP>
```

### ACTION `remove`

Removes user from whitelist table

### params

- `@param {name} account` - EOSIO account name to whitelist
- `@param {name} service` - DSP service
- `@param {name} package` - DSP package name

### example

```bash
cleos push action <DSP> remove '["myaccount","ipfsservic1","package1"]' -p <DSP>
```


### ACTION `checklist`

Checks if account name is authorized to use this package

### params

- `@param {name} account` - EOSIO account name to whitelist
- `@param {name} service` - DSP service
- `@param {name} package` - DSP package name

### example

```bash
cleos push action <DSP> checklist '["myaccount","ipfsservic1","package1"]' -p <DSP>
```

### TABLE `whitelist`

Contains all information related to the whitelist

### params

- `@param {unit64_t} id`  - Identifier for whitelist entry
- `@param {name} account` - EOSIO account name to whitelist
- `@param {name} service` - DSP service
- `@param {name} package` - DSP package name

### example

```json
{
  "id": 0,
  "account": "myaccount",
  "service": "ipfsservice1",
  "package": "package1"
}
```
