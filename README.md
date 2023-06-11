# Avax-Eth Assignment

Going to use our configured subnet created on our local network using hyperSDK.

## Description

Going to use the initial repository of hypersdk to configure and launch our own subnet in our local network and work on it.

## Getting Started

### note:

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
   ``./scripts/build.sh`` or ``bash ./scripts/run.sh``

### Executing program

