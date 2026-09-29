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

# fields

Required fields also required by citation file format:

- `title`: string, name of software
- `message`: string, one-line description of what the software does
- `type`: required in cff only for references.
  string, either "package" or "jll".
  A "package" is something we can "add" in pkg mode within julia's REPL.
  A "jll" is a package that...
  possibly in the future, to be listed under Resources:
  "pipeline", "tutorial", "app", "database"

Other required fields:

- `url`: string starting with one of `https://`, `http://`,
  `ftp://` or `sftp://` (following cff)
- `version`: string or number, e.g. "1.2.0" or 1.2
- `date-released`: date the software (at that version) was released.
  format: "yyyy-mm-dd"
- `registered`: boolean.
  true if the software is in the general julia registry, which is here:
  "https://github.com/JuliaRegistries/General"
- `uuid`: for registered packages, "notregistered" otherwise.
- `task`: array of arrays, to list the tasks (steps within a
  phylogenetic pipeline) that the software can perform.
  Each item should be an array of subtasks.
  Each subtask could of the form: `key: "one-line summary"`.
  Keywords should match those in the website "Task" box.
  See below for the allowed task and subtasks names.
- `date-curated`: date this `yaml` record was created or last updated by a human
  -- *not* the last update of the software itself!
  "0000-00-00" if uncurated, that is, if the `yaml` file was created or updated
  by an LLM and was not yet validated by a human.

Optional fields:

- `date-updated`: date of last edit update of the software on its main branch,
  such as date of last commit on the main (or master) branch.
  This could be later than `date-released`.
- `source-url`: for binary wrappers (like jll), url of source code
  from which binaries are built
- `authors`: array of authors
- `abstract`: string. summary of what the software does,
  to complement the one-line `message`.
- `graphtype`: array of keywords (super-short strings),
  to complement tasks and subtasks (which focus on steps in a pipeline)
  to let users search for the type of graphs that the software can handle.
  Standard keywords:
  "tree", "network", "split network", "admixture graph",
  "ARG", "ancestral recombination graph", "mutation tree", "transmission tree",
  "unrooted", "rooted", "multirooted",

# tasks and subtasks

task are at the primary level
subtasks are at the secondary level.

1. phylogenies:
  - read-phylogenies:
  - manipulate-phylogenies:
  - visualize-phylogenies:
  - compare-phylogenies:
  - summarize-phylogenies:
2. data-for-phylogenetics:
  - read-alignments:
  - summary-statistics:
3. phylogeny-building:
  - simulate-phylogenies:
  - infer-phylogenies:
  - phylogenies-with-time:
4. phylogenetic-comparative-methods:
  - trait-evolution:
  - trait-simulation:
  - diversification:
5. phylogenetics-in-specific-fields:
  - genetree-speciestree:
  - species-delimitation:
  - gene-duplications:
  - morphometrics:
  - time-series-and-paleontology:
  - community-and-microbial-ecology:
  - phyloclimatic-modeling:
  - population-genetics:
  - phylogeography-and-biogeography:
  - epidemiology:
  - omics:
6. interact-with-external-resources:
