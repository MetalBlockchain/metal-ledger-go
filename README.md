# metal-ledger-go

_Golang SDK for Using the [Metal Ledger App](https://github.com/MetalBlockchain/ledger-app-metal)_

## Example
```golang
device, err := Connect()
if err != nil {
  panic(err)
}

// Get version
version, commit, name, err := device.Version()
if err != nil {
  panic(err)
}
fmt.Printf("version: %s commit: %s name: %s\n", version, commit, name)

// Get Tahoe Address
address, err := device.Address("tahoe", 0, 0)
if err != nil {
  panic(err)
}
fmt.Printf("address: %s\n", address)

// Sign Hash
rawHash := hashing.ComputeHash256([]byte{0x1, 0x2, 0x3, 0x4})
suffixes := [][]uint32{{0, 1}, {0, 3}}
sigs, err := device.SignHash(rawHash, suffixes)
if err != nil {
  panic(err)
}
```

## TODO
* Add X-Chain Support (change indices)
* Add C-Chain Support
* Support Transaction Parsing (only sign hashes right now)

**NOTE: THIS PROJECT IS ACTIVELY DEVELOPED AND MAY INCUR BREAKING CHANGES**
