# Repolex Knowledge Graph of colcon/colcon-powershell

RDF knowledge graph data for [colcon/colcon-powershell](https://github.com/colcon/colcon-powershell), parsed by [repolex](https://repolex.ai).

> **Note**: This data is experimental and subject to change without notice.

## How to use this data

The easiest way to get started is to install the [rlex](https://github.com/repolex-ai/rlex) query tool:

```bash
cargo install --git https://github.com/repolex-ai/rlex
```

Verify the install:

```bash
rlex --help
```

**rlex is designed to be used primarily by LLMs in a terminal.** Start up your favorite AI assistant and ask it to use rlex. It handles the SPARQL — you just ask questions in plain English.

To load this repo's data:

```bash
rlex download colcon/colcon-powershell
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 5268900f0e4ef49a07c24f43214f991852442c05
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 5268900f0e4ef49a07c24f43214f991852442c05
│           └── chunk-001.nq.gz
├── blob
│   ├── 0c724e1d9175f2b26ca836f30a052cf193d266e2.nq.gz
│   ├── 0f17157ed42b486a0c57cbffddd97987a4844e6b.nq.gz
│   ├── 19167c20afc525a8d682feeffb6656a0ba4b8d38.nq.gz
│   ├── 19b7335f3bbecd199c87e30a792d9cb0a1b8d0de.nq.gz
│   ├── 1bcc06fcc85a56f4dbf078b4851e67d0b6598ab3.nq.gz
│   ├── 326bb66d4c74f0cf8cf0dfc4e79909001f37da84.nq.gz
│   ├── 350de6788892ae31c9cb9be0ff2bc42aead56687.nq.gz
│   ├── 5ba4973a27c8f576c859e067c657a98605df1c11.nq.gz
│   ├── 62bc2d71e0f0dd85ce64a5bc98f99c4d7f332ce3.nq.gz
│   ├── 630c8deb7271ba4b0a9a0b0ecf5b38b45d700a96.nq.gz
│   ├── 8cdf0340dc8ad6a00e19ec323d22c04150e87a22.nq.gz
│   ├── 8d315d51e4f6e4f533a08823b5cc3627e9540cc2.nq.gz
│   ├── b65ba1127a37f1ec181812ebab2ca73bd59a7e11.nq.gz
│   ├── cba4bfeaed0719a4d2593b88ca0aa153dac9ea45.nq.gz
│   ├── d645695673349e3947e8e5ae42332d0ac3164cd7.nq.gz
│   ├── db92ec8b4a21624ccbcbc180610812ce16485c64.nq.gz
│   ├── dffe460f162da9929178a7ce342532e7ba896425.nq.gz
│   ├── e535729189ac71b626211c8b42a7571cbcb3e7d7.nq.gz
│   ├── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
│   ├── e82fd0b0abbf1472480d19d468efe7819276e80d.nq.gz
│   └── eca76bf1e2d2b5b65bf3872ea711d1afc2c92cda.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 5268900f0e4ef49a07c24f43214f991852442c05.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 29 files
```

| Directory | What it contains |
|-----------|-----------------|
| `blob/` | Per-file AST graphs, content-addressed by git blob SHA. Each file in the source repo gets its own graph. |
| `aggregate/ast/` | Combined AST graph per parsed commit. Merges all blob graphs for a snapshot of the entire codebase at that point. |
| `aggregate/lsp/` | Language Server Protocol enrichment: resolved symbols, definitions, references, and type information. |
| `aggregate/dataflow/` | Interprocedural data flow edges between functions and modules. |
| `aggregate/repolex/` | Combined graph (AST + LSP + dataflow) per commit. |
| `commit/` | Git commit metadata (author, date, message, parent links). |
| `branch/` | Branch metadata. |
| `tag/` | Tag metadata. |
| `filetree/` | File tree snapshots per commit (which files existed and their blob SHAs). |
| `audit/` | Code architecture and graph audit reports per commit. |

## Source repository

[colcon/colcon-powershell](https://github.com/colcon/colcon-powershell)

---
*Parsed on 2026-10-17 by [repolex](https://repolex.ai)*
