# Pending Upload Bundle

This folder is intentionally kept separate from the main implementation so it can be uploaded to a friend or collaborator repository without disturbing the existing working tree.

## Purpose

This bundle collects the remaining distributed-consensus handoff work and organizes it in a way that is easy to merge into the earlier storage and RPC changes.

## Connection to the existing project

The bundle references the following project modules:

- `proto/lsmdb/v1/common.proto` for shared metadata and node status types
- `proto/lsmdb/v1/command.proto` for replicated command payloads
- `proto/lsmdb/v1/node.proto` for node and cluster RPC contracts
- `proto/CMakeLists.txt` for the generated build inputs
- `consensus/include/lsmdb/consensus/raft_proposer.h` for the leader/election contract used by the write path

## Included files

- `remaining_work.md` — handoff notes for the outstanding Raft integration work
- `raft_handoff.proto` — standalone Raft RPC contract that matches the project’s existing proto style
- `merge_instructions.md` — simple commands for pushing and merging this bundle into another GitHub repo

## Upload recommendation

Commit this folder as a dedicated handoff branch or a single patch so the recipient repo can review it as an isolated addition rather than a rewrite of the main implementation.
