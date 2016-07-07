## SYNOPSIS

```
git clean-stale-local [-n|--dry-run]
```

This contrib script is to be run inside a local Git repo. It looks for local branches *merged into the default branch* that track now-pruned remote branches on `origin`, and deletes these refs.

Yes, this assumes your main remote is `origin`.

No, it doesn't assume your default branch is `master`: it will look at your locally cached ref for `origin/HEAD` and, if there is none, will fetch that from the `origin` remote itself (failing that, it'll abort).

You can use the traditional `-n` / `--dry-run` flag to list the would-be removals without running them.
