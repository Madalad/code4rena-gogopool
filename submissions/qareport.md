# QA Report

## Events missing `indexed` parameters

Index event fields make the field more quickly accessible to off-chain tools that parse events. However, note that each index field costs extra gas during emission, so it’s not necessarily best to index the maximum allowed per event (three fields).

Each event should use three indexed fields if there are three or more fields, and gas usage is not particularly of concern for the events in question. If there are fewer than three fields, all of the fields should be indexed.

- https://github.com/code-423n4/2022-12-gogopool/blob/main/contracts/contract/Storage.sol#L12
