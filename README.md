# drawings_v2

New design for UAV — SolidWorks parts, assemblies, and drawings.

## Repository structure

```
parts/           Individual SolidWorks part files (.SLDPRT)
assemblies/       Assembly files (.SLDASM)
drawings/         Drawing sheets (.SLDDRW) and exported PDFs
docs/             Documentation, BOMs, notes
docs/renders/     Rendered images / screenshots for reference
```

## Requirements

- SolidWorks (version TBD — note the version here once confirmed, to avoid downgrade issues between contributors)
- [Git LFS](https://git-lfs.com/) — required to clone/pull this repo correctly, since CAD files are tracked via LFS

## Getting started

```bash
git clone https://github.com/asotek-iha/drawings_v2.git
cd drawings_v2
git lfs install
git lfs pull
```

## Working with SolidWorks files

- SolidWorks files are binary and do not diff/merge like text — **avoid two people editing the same file at the same time**. Coordinate in advance (issue, chat) on who owns a given part/assembly during active work.
- Commit early and often on stable, working states (parts that open and rebuild cleanly) rather than mid-edit states.
- Do not commit files with unresolved rebuild errors when possible; note known issues in the commit message if you must.
- Close SolidWorks before pulling changes to avoid file lock conflicts.

## Commit message convention

```
<type>: <short summary>

[optional longer description]
```

Types:
- `add` — new part/assembly/drawing
- `update` — geometry or dimension change to an existing file
- `fix` — corrects an error (bad mate, wrong dimension, broken reference)
- `docs` — README/TODO/documentation only
- `refactor` — renaming, reorganizing files/folders without design change

Examples:
- `add: wing spar part (spar_main.SLDPRT)`
- `update: fuselage assembly — widen battery bay by 10mm`
- `fix: broken mate in tail assembly after spar update`

## Status

See [TODO.md](TODO.md) for current task list.
