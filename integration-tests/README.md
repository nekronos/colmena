# Integration Tests

A set of integration tests using the NixOS test framework.
The flake exposes each test as a check. Run one with `nix build .#checks.<system>.<check>`, or all of them with `nix flake check`.
