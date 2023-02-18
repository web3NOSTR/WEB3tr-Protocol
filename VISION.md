# WEB3tr a web3 version of NOSTR 

## Why a web3 specific version?
Because Nostr is built around bitcoin tooling, using bitcoin signatrues for use by bitcoin users. 

The web3 world would benefit from a version of nostr that is built around web3 addresses as identities, uses web3 native signatures and verifications shemes. 

This opens up use cases that can interwine with smart contracts along any evm compatible blockchain. 




## Quick primer on nostr. 
Before I explain the design pricinples of WEB3tr we must first explain the original nostr spec.

There is a great explanation of what nostr is available [here](https://github.com/rajarshimaitra/rust-nostr/blob/main/VISION.md)
(This is where the following examples are taken from)

Nostr server stores and retrieves a simple data structure called an Event. 
This is an event:

```
{
  "id": <32-bytes sha256 of the the serialized event data>
  "pubkey": <32-bytes hex-encoded public key of the event creator>,
  "created_at": <unix timestamp in seconds>,
  "kind": <integer>,
  "tags": [
    ["e", <32-bytes hex of the id of another event>, <recommended relay URL>],
    ["p", <32-bytes hex of the key>, <recommended relay URL>],
    ... // other kinds of tags may be included later
  ]
  "content": <arbitrary string>,
  "sig": <64-bytes signature of the sha256 hash of the serialized event data, which is the same as the "id" field>,
}
```

Events are signed using Shnorr signatures. Basically the signtature is the same as a Bitcoin Taproot BIP340 signature. 



## WEB3tr changes

Signatures on WEB3tr use the same signatures as ethereum does for verifying transactions. This helps with interopability on any WEB3tr app. 

Public keys on WEB3tr are valid ethereum addresses. Any EOA on ethereum is an already existing WEB3tr account. 

Signing WEB3tr events use already established web3 developer patterns so available from any web3 wallet. Sign with a hardware wallet or web browser. 



## WEB3tr message signing 

Message signing adopts EIP-191 standard. https://eips.ethereum.org/EIPS/eip-191

oldschool signatures https://web3py.readthedocs.io/en/latest/web3.eth.html#web3.eth.Eth.sign
modern eip191 https://eth-account.readthedocs.io/en/stable/eth_account.html#eth_account.account.Account.sign_message

eip 712 standard
https://eips.ethereum.org/EIPS/eip-712




Metamask has 6 methods of singing messages 
https://docs.metamask.io/guide/signing-data.html#signing-data-with-metamask
eth_sign
personal_sign
signTypedData (currently identical to signTypedData_v1)
signTypedData_v1
signTypedData_v3
signTypedData_v4

Only personal_sign works with hardware wallets. 
https://github.com/ethereum/go-ethereum/pull/2940









