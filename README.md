# Repolex Knowledge Graph of napari/napari-svg

RDF knowledge graph data for [napari/napari-svg](https://github.com/napari/napari-svg), parsed by [repolex](https://repolex.ai).

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
rlex download napari/napari-svg
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── e41542add2efdfe401522be9bc05a4e46b3c3d73
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── e41542add2efdfe401522be9bc05a4e46b3c3d73
│           └── chunk-001.nq.gz
├── blob
│   ├── 0fe48323da8a8889607e17b13ebf771e949e08cc.nq.gz
│   ├── 31d11d58019c4d36e2221e6c854ead58a0c9677c.nq.gz
│   ├── 459230e0a6c15da65835b67e80e5393b8f79b664.nq.gz
│   ├── 49194a2ebd069d0d6a7ff14a195150446baf47ad.nq.gz
│   ├── 69e5c1bee5f084e1dfc64579e3884c096b68be21.nq.gz
│   ├── 6bc7dced9611fb2c19e6c229bc13a8349a07b15a.nq.gz
│   ├── 75b231e0ef00a28c2d8c5c0c16b2382abf6246b4.nq.gz
│   ├── 794064db7533a87dea554174bd747a79c9773161.nq.gz
│   ├── 8412addb3cdf4ae132ce71fee4bdd90f625fbb6b.nq.gz
│   ├── 91cb22e2380ffbc9eef52631f1aaf83bc2bde7f7.nq.gz
│   ├── 9540ec1103fe519ab1f56773bc41af0250863360.nq.gz
│   ├── a189916e6470b8e9439288b53c6e4704a8d67210.nq.gz
│   ├── ba1849cb6f65d94223a49597ce8514c68070f3ac.nq.gz
│   ├── bef068f7ecd297d298115903ac9de3ec26d913db.nq.gz
│   ├── ca44497dfc342e94e559eee2c2eeb5922a7328c5.nq.gz
│   ├── d1c42c253b26d457797b03f3590aa600879c43d2.nq.gz
│   ├── dc1b4ae50cc774b8a1c2ccac83eeb67a5261b909.nq.gz
│   ├── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
│   ├── e6c3db86bbf5e9a1752ce57e4e126ebb208b73b3.nq.gz
│   ├── f1b5b531dcfdbaf0ea7dcf19b5cd991f23a00cba.nq.gz
│   └── f4f8ac48bcc18b69231760309200fe77cd389fd6.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── e41542add2efdfe401522be9bc05a4e46b3c3d73.nq.gz
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

[napari/napari-svg](https://github.com/napari/napari-svg)

---
*Parsed on 2026-10-28 by [repolex](https://repolex.ai)*
