# Avax-Eth Assignment

Going to use our configured subnet created on our local network using hyperSDK.

## Description

Going to use the initial repository of hypersdk to configure and launch our own subnet in our local network and work on it.

## Getting Started

### Note:

You need to create your own build for checking as build file are greater than 25mb and does not have an extention so i can't upload :-( 
and same with the test folder you can take it from the official repo as well.

## Initialize

1. To get started, first you need to go to const/const.go and give your native token of your subnet a name and a symbol, etc (install GO).
2. Now create a controller/registry.go file and add your mint, create and transfer initializations.
3. Now run this command inside the root folder.
   ``go mod tidy``
   it will download all the dependency.
4. Then run this script to run the configurations set by you and all the testing are done autmatically.
   ``./scripts/run.sh`` or ``bash ./scripts/run.sh``
5. Then after success run this to create the build from above.
   ``./scripts/build.sh`` or ``bash ./scripts/build.sh``
   
_This command will put the compiled CLI in `./build/token-cli`._
   

### Executing program

## Demos

_By default, this allocates all funds on the network to
`token1rvzhmceq997zntgvravfagsks6w0ryud3rylh4cdvayry0dl97nsjzf3yp`. The private
key for this address is
`0x323b1d8f4eed5f0da9da93071b034f2dce9d2d22692c172f3cb252a64ddfafd01b057de320297c29ad0c1f589ea216869cf1938d88c9fbd70d6748323dbf2fa7`.
For convenience, this key has is also stored at `demo.pk`._


Lastly, you'll need to add the chains you created and the default key to the
`token-cli`. You can use the following commands from this location to do so:
```bash
./build/token-cli key import demo.pk
./build/token-cli chain import-anr
```

_`chain import-anr` connects to the Avalanche Network Runner server running in
the background and pulls the URIs of all nodes tracking each chain you
created._

### Mint and Trade
#### Step 1: Create Your Asset
First up, let's create our own asset. You can do so by running the following
command from this location:
```bash
./build/token-cli action create-asset
```

When you are done, the output should look something like this:
```
database: .token-cli
address: token1rvzhmceq997zntgvravfagsks6w0ryud3rylh4cdvayry0dl97nsjzf3yp
chainID: dL5FhBfaR4zE3s6xwtisj4C2aGw4dLGQMfMjM2BJgqkgcbG9t
metadata (can be changed later): Goldcoin
continue (y/n): y
✅ txID: ywfmASBCPjXbmVEeTM8u8CCZ82tkN2t9yKg7hteG9w2M2ffza
```

_`txID` is the `assetID` of your new asset._

The "loaded address" here is the address of the default private key (`demo.pk`). We
use this key to authenticate all interactions with the `tokenvm`.

#### Step 2: Mint Your Asset
After we've created our own asset, we can now mint some of it. You can do so by
running the following command from this location:
```bash
./build/token-cli action mint-asset
```

When you are done, the output should look something like this (usually easiest
just to mint to yourself).
```
database: .token-cli
address: token1rvzhmceq997zntgvravfagsks6w0ryud3rylh4cdvayry0dl97nsjzf3yp
assetID: ywfmASBCPjXbmVEeTM8u8CCZ82tkN2t9yKg7hteG9w2M2ffza
✔ assetID: ywfmASBCPjXbmVEeTM8u8CCZ82tkN2t9yKg7hteG9w2M2ffza
metadata: Goldcoin supply: 0
recipient: token1rvzhmceq997zntgvravfagsks6w0ryud3rylh4cdvayry0dl97nsjzf3yp
amount: 100000
continue (y/n): y
✅ txID: 2tcDV5K6NxiQF97Fd5KSXCSz8GjGZP8Bn6qqXY6jEpz2sTiVB6
```

#### Step 3: View Your Balance
Now, let's check that the mint worked right by checking our balance. You can do
so by running the following command from this location:
```bash
./build/token-cli key balance
```

When you are done, the output should look something like this:
```
database: .token-cli
address: token1rvzhmceq997zntgvravfagsks6w0ryud3rylh4cdvayry0dl97nsjzf3yp
chainID: dL5FhBfaR4zE3s6xwtisj4C2aGw4dLGQMfMjM2BJgqkgcbG9t
assetID (use TKN for native token): ywfmASBCPjXbmVEeTM8u8CCZ82tkN2t9yKg7hteG9w2M2ffza
uri: http://127.0.0.1:29517/ext/bc/dL5FhBfaR4zE3s6xwtisj4C2aGw4dLGQMfMjM2BJgqkgcbG9t
metadata: Goldcoin supply: 100000 warp: false
balance: 100000 ywfmASBCPjXbmVEeTM8u8CCZ82tkN2t9yKg7hteG9w2M2ffza
```
