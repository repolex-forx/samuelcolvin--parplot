# Repolex Knowledge Graph of samuelcolvin/parplot

RDF knowledge graph data for [samuelcolvin/parplot](https://github.com/samuelcolvin/parplot), parsed by [repolex](https://repolex.ai).

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
rlex download samuelcolvin/parplot
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 236f42423c91becb422bda84b452bb4bb41b1c6e
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 236f42423c91becb422bda84b452bb4bb41b1c6e
│           └── chunk-001.nq.gz
├── blob
│   ├── 0302847d41a5d070d5f21e5cd2fc0fa74372f562.nq.gz
│   ├── 24ee5b1be9961e38a503c8e764b7385dbb6ba124.nq.gz
│   ├── 7e8f40fd8e79aac08b1c52af6101d0f7b25f0c9b.nq.gz
│   ├── 90076f16a6888a5f7d676461ff3a9a6dedfd1170.nq.gz
│   ├── a01521bb5ea8b1a1c0484cfedb57073002d124d7.nq.gz
│   ├── a3efca2fc95c2c292bca494520e780a344c3c2ff.nq.gz
│   ├── d6802c75e77756311f8b828fba194e75563f562a.nq.gz
│   ├── e5871c5d3ccbd9681be3f04cd73875c3c4c0452e.nq.gz
│   └── f7878410a1f80dd69d3573070993414531c5d3db.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 236f42423c91becb422bda84b452bb4bb41b1c6e.nq.gz
└── tag
    └── tag.nq.gz

11 directories, 15 files
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

[samuelcolvin/parplot](https://github.com/samuelcolvin/parplot)

---
*Parsed on 2026-10-11 by [repolex](https://repolex.ai)*
