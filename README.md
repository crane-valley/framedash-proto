# @framedash/proto

Protobuf definitions (`.proto` files) for the Framedash telemetry protocol.

## Schema

`telemetry.proto` defines the wire format for SDK-to-server communication:

- `TelemetryBatch` — Top-level message containing an array of events
- `TelemetryEvent` — Individual telemetry event with player/session/map/position/performance fields
- Camera rotation fields (`camera_yaw`, `camera_pitch`) — Optional, presence-tracked

## Using the schema

The module is configured for [Buf](https://buf.build/) (see `buf.yaml`). Vendor
`framedash/v1/telemetry.proto` (or add this module as a Buf dependency) and
generate bindings for your language with `buf generate` or `protoc` -- no
`protoc` binary is required when using Buf. The Framedash UE5 SDK generates its C
bindings with [nanopb](https://github.com/nanopb/nanopb) (`pip install nanopb==0.4.9.1`).
