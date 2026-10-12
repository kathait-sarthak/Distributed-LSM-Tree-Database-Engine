# Remaining Raft handoff work

This file keeps the unfinished coordination work in a separate place so it can be reviewed and attached to the earlier storage and RPC progress without disturbing the main code path.

## What is still pending

The project already contains the storage layer, distributed gRPC clients, write handler hooks, and consensus interfaces. The missing contract layer was the Week 5/6 Raft RPC definition.

## How it connects to the previous work

- `proto/lsmdb/v1/common.proto` provides shared `NodeInfo`, `RequestMeta`, and `Status`.
- `proto/lsmdb/v1/command.proto` provides the replicated log payload format.
- `consensus/include/lsmdb/consensus/raft_proposer.h` defines the leader-election and replication contract expected by the write path.
- `proto/lsmdb/v1/raft.proto` adds the actual RPCs used to implement that contract.
- `proto/CMakeLists.txt` includes the new proto so the generated C++/gRPC code is part of the build.

## Files added or updated

- `proto/lsmdb/v1/raft.proto`
- `proto/CMakeLists.txt`
- `proto/lsmdb/v1/node.proto`

## Recommended next step

Implement the Raft service stubs and peer manager integration against these types, then connect the leader election / append path to the existing `RaftProposer` interface.
