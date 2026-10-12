# Repolex Knowledge Graph of datasette/datasette-tailscale

RDF knowledge graph data for [datasette/datasette-tailscale](https://github.com/datasette/datasette-tailscale), parsed by [repolex](https://repolex.ai).

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
rlex download datasette/datasette-tailscale
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 7f5ac3e3ebe56caf7f294c1c871a650619eaeb8e
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 7f5ac3e3ebe56caf7f294c1c871a650619eaeb8e
│           └── chunk-001.nq.gz
├── blob
│   ├── 04920665e89e23e8b961bb5419c695e63c73e79a.nq.gz
│   ├── 261eeb9e9f8b2b4b0d119366dda99c6fd7d35c64.nq.gz
│   ├── 397b11a26389ff779f1e9336917290eebf5a2260.nq.gz
│   ├── 467da60574868f5de29f6a2af936cad80a30d528.nq.gz
│   ├── 4ea05b444f015c2ea28f89c686e54d4ecf3e89dd.nq.gz
│   ├── 723aebcfec10e4b57875a7a09b7dc7e88512ecea.nq.gz
│   ├── 90a5c661c0c087e1994cfde9164bd65cdf0baedf.nq.gz
│   ├── a786eaded181011f35076ba817bcbe33dba39979.nq.gz
│   └── f8bb523d5efc81fdd483d95f703cb484272bb97b.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 7f5ac3e3ebe56caf7f294c1c871a650619eaeb8e.nq.gz
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

[datasette/datasette-tailscale](https://github.com/datasette/datasette-tailscale)

---
*Parsed on 2026-10-12 by [repolex](https://repolex.ai)*
