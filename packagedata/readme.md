This folder contains one file per package or binary wrapper
to be listed in the task view.
The format follows that of the `cff`
[Citation File Format](https://zenodo.org/records/5171937) and its
[schema guide](https://github.com/citation-file-format/citation-file-format/blob/main/schema-guide.md),

We adopt the same fields and subfields are required
by `cff`, as much as possible, but need extra fields. 
see
[valid-keys](https://github.com/citation-file-format/citation-file-format/blob/main/schema-guide.md#valid-keys)


Required fields shared with citation file format:

- `title`: name of software


Required fields / keys not shared with citation file format:

- `tasks`: list of tasks (categories) within a phylogenetic
  pipeline that the software can perform.

Optional fields:

- `graphtype`: type of evolutionary graphs that the software supports?
  e.g. split implicit networks,
  rooted and semidirected explicit networks,
  mutation trees (internal nodes can be labeled with data),
  ancestral recombination graphs
