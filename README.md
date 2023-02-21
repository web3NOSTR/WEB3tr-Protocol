# WEB3tr-Protocol
The definition for the WEB3tr standard. WEB3tr is a web3 focused version of nostr. 


**Why a web3 specific version?**

Because Nostr is built around bitcoin tooling, using bitcoin signatrues for use by bitcoin users. 

The web3 world would benefit from a version of nostr that is built around web3 addresses as identities, uses web3 native signatures and verifications shemes. 

This opens up use cases that can interwine with smart contracts along any evm compatible blockchain. 



## TLDR: How web3NOSTR works

web3NOSTR is built around a simple data structure called an "event". Events are signed and can verified to be authored by a specific ethereum address. 
Events are sent from clients to relays which store and serve the event to any client that is subscribed to a specific user. 

This is what a web3NOSTR event looks like:

```
{
  "id": <32-bytes (64 hex) keccak-256* of the the serialized event data>
  "address": <20-bytes (40 hex characters prepended by 0x) hex-character encoded ethereum address>,
  "created_at": <unix timestamp in seconds>,
  "kind": <integer>,
  "tags": [
    ["e", <32-bytes hex of the id of another event>, <recommended relay URL>],
    ["p", <32-bytes hex of the key>, <recommended relay URL>],
    ... // other kinds of tags may be included later
  ]
  "content": <arbitrary string>,
  "sig": <65-bytes signature of the keccak-256 hash of the serialized event data, which is the same as the "id" field>,
}
```


* [keccak-256](https://ethereum.org/en/glossary/#keccak-256)


## Relay network 

Relays are simple websocket servers which verify incoming events as containing a valid signature. There is no account creation required. 
Clients are able to subscribe to a specific user and will recive new events coming from a specific user. 



