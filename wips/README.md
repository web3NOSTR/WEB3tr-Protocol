# WIPS- WEB3tr Implementation Possibilities 

WIPS stand for WEB3tr Implementation Possibilities. They exist to document what may be implemented by WEB3tr-compatible relay and client software.
WEB3tr is heavily influenced by nostr, whos implementation possibilities can be found here: [https://github.com/nostr-protocol/nips](https://github.com/nostr-protocol/nips)


- [WIPS-01: Basic protocol flow description](01.md)


## Event Kinds
| kind          | description                      | WIP                     |
| ------------- | -------------------------------- | ----------------------- |
| 0             | Metadata                         | [1](01.md) |
| 1             | Short Text Note                  | [1](01.md)              |
| 2             | Recommend Relay                  | [1](01.md)              |



## Message types

### Client to Relay
| type  | description                                         | WIP         |
|-------|-----------------------------------------------------|-------------|
| EVENT | used to publish events                              | [1](01.md)  |
| REQ   | used to request events and subscribe to new updates | [1](01.md)  |
| CLOSE | used to stop previous subscriptions                 | [1](01.md)  |



### Relay to Client
| type   | description                                             | WIP         |
|--------|---------------------------------------------------------|-------------|
| EVENT  | used to send events requested to clients                | [1](01.md)  |
| NOTICE | used to send human-readable messages to clients         | [1](01.md)  |



# Standardized Tags

| name       | value                   | other parameters  | WIP                      |
| ---------- | ----------------------- | ----------------- | ------------------------ |
| e          | event id (hex)          | relay URL, marker | [1](01.md) |
| p          | pubkey (hex)            | relay URL         | [1](01.md)               |



## License

All WIPs are public domain.
