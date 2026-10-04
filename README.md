# uke-core-meta

Minimal console system dependencies and profile-aware package composition for Xiaomi Pad 7 / POCO Pad X1 (`uke`, SM7675).

This is an initial project-owned source and packaging repository. The manifest
lists the intended packages, Uke evidence gates and current build readiness.
There is no functional hardware payload or device acceptance at this checkpoint.

## Package scope

- `uke-core-meta`

Nabu reference families: `nabu-core-meta`.
These are process references; Uke wiring, firmware and runtime behavior require
independent implementation and validation.

## Required validation

- Resolve only available Uke package families.
- Audit the complete installed closure for Python.
- Separate kernel package installation from boot selection.

The first packaging target is Fedora Rawhide AArch64 in
[uke-linux-test COPR](https://copr.fedorainfracloud.org/coprs/mcc45tr/uke-linux-test/).
DEB and Alpine APK targets require their own native rules later.
Unimplemented targets fail explicitly rather than producing placeholder RPMs.

Use `make validate` to check this repository's manifest contract. Native device
applications use C++; upstream C/assembly interfaces retain their original
languages. Host automation uses Bash or Make. Python does not enter tablet
payloads. Source archives belong in `referances/`, development in `src/`.
Public records exclude personal paths, unit identifiers and calibration data.

See [the roadmap](docs/ROADMAP.md), [source policy](docs/SOURCE-POLICY.md) and
[manifest](manifests/component.json). New material findings are recorded in
`docs/lessons/`; source, package, emulation and physical evidence stay distinct.
