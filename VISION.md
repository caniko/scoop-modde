# scoop-modde vision

This repository is a single-manifest Scoop bucket for `modde`, the cross-platform
game mod manager published from the `rs-modde` project. The only artifact here
is `bucket/modde.json`, which points Scoop at the Windows release archive and
declares the `modde` and `modde-ui` binaries. It is a packaging repository, not
a codebase.

## Problem

Scoop installs Windows tools from bucket manifests. Publishing `modde` that way
needs a separate, reviewable manifest that names the release archive, its hash,
its license, and the executables inside it, so a Scoop user can install and
upgrade without downloading and unpacking by hand.

## Scope

- `bucket/modde.json`: version, description, homepage, license, and the 64-bit
  Windows archive with its `bin` list.
- The manifests are JSON and are the whole deliverable; `nix/treefmt.nix` exists
  only so the tree is formatted with prettier like the rest of the fleet.

## Direction

Not yet documented. The checked-in manifest pins version 0.7.0, and its `hash`
field is still a zero placeholder, so the manifest has not yet been pinned to a
real archive.

## Place in the fleet

No canix consumer was found. `modde` itself is built in `rs-modde`; this bucket
is one of its distribution channels alongside the project's own release
artifacts.
