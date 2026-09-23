This folder contains one file per package or binary wrapper
to be listed in the task view.
The format follows that of the `cff`
[Citation File Format](https://zenodo.org/records/5171937) and its
[schema guide](https://github.com/citation-file-format/citation-file-format/blob/main/schema-guide.md),

We adopt the same fields and subfields are required
by `cff`, as much as possible, but
* we require some extra fields, and
* some fields required by `cff` are *not* required here:
  - `cff-version`
  - `authors`: this may not available easily, or difficult to
    determine for command-line programs packaged as julia artifacts
    (original program's author, versus artifact's author?)

see
[valid-keys](https://github.com/citation-file-format/citation-file-format/blob/main/schema-guide.md#valid-keys)


Required fields also required by citation file format:

- `title`: string, name of software
- `message`: string, one-line description of what the software does
- `type`: required in cff only for references.
  would we want to use this to distinguish packages from
  binary wrappers, from apps, perhaps databases in the future, etc.?

Other required fields:

- `url`: string starting with one of `https://`, `http://`,
  `ftp://` or `sftp://` (following cff)
- `version`: string or number, e.g. "1.2.0" or 1.2
- `date-released`: date the software (at that version) was released.
  format: "yyyy-mm-dd"
- `registry`: string.
  If the software is in the official julia registry, use this:
  "https://github.com/JuliaRegistries/General"
  ?? or should we use `juliaregistry`: boolean?
  It would be less informative, but possibly sufficient.
- `task`: array of arrays, to list the tasks (steps within a
  phylogenetic pipeline) that the software can perform.
  Each item should be an array of subtasks.
  Each subtask could of the form: `key: "one-line summary"`.
  Keywords should match those in the website "Task" box.
- `lastedited`: last date when this entry was checked --
  *not* the last update of the software itself!

Optional fields:

- `lastupdated`: date of last software update,
  which could be later than `date-released`
- `authors`: array of authors
- `abstract`: string. summary of what the software does,
  to complement the one-line `message`.
- `graphtype`: type of evolutionary graphs that the software supports?
  e.g. split implicit networks,
  rooted and semidirected explicit networks,
  mutation trees (internal nodes can be labeled with data),
  ancestral recombination graphs
- `uuid`: for official julia packages?
