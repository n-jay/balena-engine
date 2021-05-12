# PRTIQL Engine

<p align="center" width="100%">
    <img width="10%" src="logo.png"> 
</p>

[![make-master](https://github.com/n-jay/balena-engine/actions/workflows/main.yml/badge.svg)](https://github.com/n-jay/balena-engine/actions/workflows/main.yml)

This is the prototype moby-based container engine for running PRTQL applications

## Disclaimer

This project is still very much a work-in-progress and not intended for everyday use.

Caution is adviced.

## Highlights

- __Small footprint__: 3.5x smaller than Docker CE, packaged as a single binary
- __Multi-arch support__: Available for a wide variety of chipset architectures, supporting everything from tiny IoT devices to large industrial gateways
- __True container deltas__: Bandwidth-efficient updates with binary diffs, 10-70x smaller than pulling layers
- __Minimal wear-and-tear__: Extract layers as they arrive to prevent excessive writing to disk, protecting your storage from eventual corruption
- __Failure-resistant pulls__: Atomic and durable image pulls defend against partial container pulls in the event of power failure
- __Conservative memory use__: Prevents page cache thrashing during image pull, so your application runs undisturbed in low-memory situations

## Motivation

It has been purpose-built for improved performance and is 
compatible with Docker containers. Based on Docker’s Moby Project, balenaEngine
supports container deltas for 10-70x more efficient bandwidth usage, has 3x
smaller binaries, uses RAM and storage more conservatively, and focuses on
atomicity and durability of container pulling.

## Transitioning from Docker CE

We left out Docker features that we saw as most needed in cloud deployments and
therefore not warranting inclusion in a lightweight IoT-focused container
engine. Specifically, we’ve excluded:

- Docker Swarm
- Cloud logging drivers
- Plugin support
- Overlay networking drivers
- Non-boltdb discovery backends (consul, zookeeper, etcd, etc.)
- Buildkit (although support can be enabled using a build tag)

Unless you depend on one of the features in Docker that balenaEngine omits, using
balenaEngine should be a drop-in replacement.

## License

PRTIQL Engine is licensed under the Apache License, Version 2.0.
