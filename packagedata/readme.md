This folder contains one file per package or binary wrapper
to be listed in the task view.
The format follows that of the `cff`
[Citation File Format](https://zenodo.org/records/5171937) and its
[schema guide](https://github.com/citation-file-format/citation-file-format/blob/main/schema-guide.md),

We adopt the same fields and subfields are required
by `cff`, as much as possible, but we require some extra fields
and we do *not* require the `cff-version` field.
see
[valid-keys](https://github.com/citation-file-format/citation-file-format/blob/main/schema-guide.md#valid-keys)


Required fields also required by citation file format:

- `title`: string, name of software
- `authors`: array of authors
- `message`: string, message for the human reader
  (what could we use this for?)
- `type`: required in cff only for references.
  would we want to use this to distinguish packages from
  binary wrappers, from apps, perhaps databases in the future, etc.?

Other required fields:

- `url`: string starting with one of `https://`, `http://`,
  `ftp://` or `sftp://` (following cff)
- `version`: string or number, e.g. "1.2.0" or 1.2
- `registry`:
  to know if the sofware is in the official julia registry??
- `tasks`: list of tasks (categories) within a phylogenetic
  pipeline that the software can perform.

- `lastupdated`

Optional fields:

- `graphtype`: type of evolutionary graphs that the software supports?
  e.g. split implicit networks,
  rooted and semidirected explicit networks,
  mutation trees (internal nodes can be labeled with data),
  ancestral recombination graphs
