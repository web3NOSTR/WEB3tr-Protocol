# WIPS- WEB3tr Implementation Possibilities 

WIPS stand for WEB3tr Implementation Possibilities. They exist to document what may be implemented by WEB3tr-compatible relay and client software.
WEB3tr is heavily influenced by nostr, whos implementation possibilities can be found here: [https://github.com/nostr-protocol/nips](https://github.com/nostr-protocol/nips)


- [WIPS-01: Basic protocol flow description](01.md)


## Event Kinds
| kind          | description                      | NIP                     |
| ------------- | -------------------------------- | ----------------------- |
| 0             | Metadata                         | [1](01.md), [5](05.md)  |
| 1             | Short Text Note                  | [1](01.md)              |
| 2             | Recommend Relay                  | [1](01.md)              |
| 3             | Contacts                         | [2](02.md)              |
| 4             | Encrypted Direct Messages        | [4](04.md)              |
| 5             | Event Deletion                   | [9](09.md)              |
| 7             | Reaction                         | [25](25.md)             |
| 40            | Channel Creation                 | [28](28.md)             |
| 41            | Channel Metadata                 | [28](28.md)             |
| 42            | Channel Message                  | [28](28.md)             |
| 43            | Channel Hide Message             | [28](28.md)             |
| 44            | Channel Mute User                | [28](28.md)             |
| 45-49         | Public Chat Reserved             | [28](28.md)             |
| 1984          | Reporting                        | [56](56.md)             |
| 9734          | Zap Request                      | [57](57.md)             |
| 9735          | Zap                              | [57](57.md)             |
| 10002         | Relay List Metadata              | [65](65.md)             |
| 22242         | Client Authentication            | [42](42.md)             |
| 24133         | Nostr Connect                    | [46](46.md)             |
| 30023         | Long-form Content                | [23](23.md)             |
| 1000-9999     | Regular Events                   | [16](16.md)             |
| 10000-19999   | Replaceable Events               | [16](16.md)             |
| 20000-29999   | Ephemeral Events                 | [16](16.md)             |
| 30000-39999   | Parameterized Replaceable Events | [33](33.md)             |



## Message types

### Client to Relay
| type  | description                                         | NIP         |
|-------|-----------------------------------------------------|-------------|
| EVENT | used to publish events                              | [1](01.md)  |
| REQ   | used to request events and subscribe to new updates | [1](01.md)  |
| CLOSE | used to stop previous subscriptions                 | [1](01.md)  |
| AUTH  | used to send authentication events                  | [42](42.md) |



### Relay to Client
| type   | description                                             | NIP         |
|--------|---------------------------------------------------------|-------------|
| EVENT  | used to send events requested to clients                | [1](01.md)  |
| NOTICE | used to send human-readable messages to clients         | [1](01.md)  |
| EOSE   | used to notify clients all stored events have been sent | [15](15.md) |
| OK     | used to notify clients if an EVENT was successuful      | [20](20.md) |
| AUTH   | used to send authentication challenges                  | [42](42.md) |





