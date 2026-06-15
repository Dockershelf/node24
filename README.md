# node24

Debian packaging for Node.js 24: monolithic `nodejs` replacement packages used by the [Dockershelf node-pipeline](../node-pipeline).

## Supported Debian suites

- `trixie`
- `unstable`

Packaging trees live under `debiandirs/<suite>/`. Changelog tracks:

- **mainline** — `changelogs/mainline/<suite>`
- **nightly** — `changelogs/nightly/<suite>`

## Build (from workspace)

Clone or seed this repo as a sibling of `node-pipeline/`, then from `node-pipeline/`:

```bash
make materialize NODE=24 DIST=trixie
make build NODE=24
```

See the [operations manual](https://github.com/Dockershelf/node-pipeline/blob/main/docs/operations.md) for new majors, version bumps, and new suites.

## Layout

| Path | Purpose |
|------|---------|
| `node/` | Upstream Node.js git submodule (`v24.x` branch) |
| `patches/` | Quilt series (usually empty for monolithic builds) |
| `debiandirs/` | Per-suite Debian packaging (`trixie`, `unstable`) |
| `changelogs/` | `mainline` and `nightly` dch history per suite |
