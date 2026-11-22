# BRACKEN Core

**Shared contracts and reusable foundations for BRACKEN components.**

BRACKEN Core is intended to hold the small set of common libraries, schemas, interfaces, and utilities needed across multiple BRACKEN services. Its purpose is to make components interoperable while keeping their implementations independently maintainable.

> **Project status:** Early-stage project. APIs and language bindings have not yet been finalized.

## Responsibilities

- Define versioned shared data structures and configuration models.
- Provide common error, logging, identity, and service metadata conventions where appropriate.
- Specify inter-process communication contracts and compatibility rules.
- Offer reusable networking and systems helpers when multiple components need the same behavior.
- Document SDK or library usage for BRACKEN services.

## What belongs here

A shared component belongs here when at least two services need the same stable behavior and a common implementation reduces ambiguity. APIs should be narrowly scoped, documented, and independently versioned when compatibility requires it. Keep service-specific policy and orchestration in the owning repository.

## What does not belong here

Core should not become a general dumping ground for code or a dependency on every internal implementation. Packet processing belongs in [bracken-data-plane](https://github.com/vayun-networks/bracken-data-plane); network configuration and routing behavior belong in [bracken-network-engine](https://github.com/vayun-networks/bracken-network-engine); management workflows belong in [bracken-control-plane](https://github.com/vayun-networks/bracken-control-plane).

## Design principles

- Favor explicit, versioned contracts over undocumented shared assumptions.
- Keep dependency direction clear and avoid circular dependencies.
- Make compatibility and deprecation decisions visible.
- Minimize transitive dependencies and avoid coupling consumers to internal details.
- Include examples and validation for public interfaces.

## Planned deliverables

The first deliverables should be a repository-wide API and versioning policy, initial service configuration and health schemas, and a clearly documented mechanism for compatibility testing. Specific languages, wire formats, and IPC mechanisms remain design decisions until adopted in an architecture proposal.

## Development

No build or test command is defined yet. Each library or schema should include focused documentation, examples, and compatibility notes. Changes to shared contracts should identify affected consumers and explain migration expectations.

## Related components

Core contracts are expected to be used by [bracken-control-plane](https://github.com/vayun-networks/bracken-control-plane), [bracken-data-plane](https://github.com/vayun-networks/bracken-data-plane), [bracken-network-engine](https://github.com/vayun-networks/bracken-network-engine), [bracken-analytics](https://github.com/vayun-networks/bracken-analytics), and other platform services as they are implemented.