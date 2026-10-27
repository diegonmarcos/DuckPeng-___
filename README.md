# DuckPeng

Registry index for the DuckPeng project (the CG hub, the cloud hub and Leaf.y) - same model as `CG`, `front` and `cloud`. This repo is an INDEX, not a container: it holds `repos.json` (the registry, a subset of git-repos-master/repos.json), `clone.sh` (pick which repos to have locally) and one committed relative symlink per member (`<member> -> ../<member>`); the actual clones live as siblings in `~/git/`.

## Members

- [CG](https://github.com/diegonmarcos/CG) - Project master for the CG family (CG-circus, CG-galaxy, CG-galaxy-gaia, CG-unity, CG-voxel-rust): its own repos.json subset plus committed symlinks, same model as front, cloud and lecole-42. Created 2026-10-26 (#1204).
- [cloud](https://github.com/diegonmarcos/cloud) - Project master for the cloud project: a repos.json subset of this file plus committed symlinks. Had a symlink here but no entry until 2026-08-20 — the drift that made `ls a_cloud/` disagree with `--list`.
- [DuckPeng-LeafY](https://github.com/diegonmarcos/DuckPeng-LeafY) - Leaf.y company site (published at /leafy/), moved from front-endeavours a_Companies/leafy (#1224); front-endeavours keeps a symlink to this repo.

## Usage

```
./clone.sh                list what exists and what does not
./clone.sh <name>...      clone those, then link them
./clone.sh --all          clone every member
./clone.sh --link         relink whatever is already cloned
./clone.sh --relink       rewrite every link from the registry
./check-repos-sot.sh      verify repos.json against git-repos-master
```

`repos.json` is a SUBSET of `~/git/git-repos-master/repos.json` (the superset index of every repo this account owns): identical name/url/private/doc fields, checked by `./check-repos-sot.sh`.
