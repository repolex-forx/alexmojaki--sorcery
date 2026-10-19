# Repolex Knowledge Graph of alexmojaki/sorcery

RDF knowledge graph data for [alexmojaki/sorcery](https://github.com/alexmojaki/sorcery), parsed by [repolex](https://repolex.ai).

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
rlex download alexmojaki/sorcery
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 65e976d66064dbdd498e29715578b1e5fdad43d5
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 65e976d66064dbdd498e29715578b1e5fdad43d5
│           └── chunk-001.nq.gz
├── blob
│   ├── 0a4b53a2005f2bad269762cc4316c3aba98518b1.nq.gz
│   ├── 10ef57259eeefee91f926ef13b448dbfb2f1eec7.nq.gz
│   ├── 115763923d6562b9315049041c1ac9af9c1cdcc8.nq.gz
│   ├── 3d5c53fa1050bfcaec410ca849290a8e0bf2c52a.nq.gz
│   ├── 6006776dbcf6d766b4ffe7e17fb31929fa692c31.nq.gz
│   ├── 60c24e571b6dc7bea56e7cf45abdc56eeee44a2a.nq.gz
│   ├── 646118bf49e2c8628e912fb529377f35ab9884f2.nq.gz
│   ├── 748b6c0597d6345a91b0066b9f6df41142b2e77f.nq.gz
│   ├── 7f1a1763ca9cebc7bc16576d353d3284ee5d3c7d.nq.gz
│   ├── 80d368191067f59966807279fd9b49d4c859f35d.nq.gz
│   ├── 85c22a540287f67bffc0c309269c0f4b6c4989eb.nq.gz
│   ├── 9c26eafe3746cd5615e8f51d042e7cc922544682.nq.gz
│   ├── b6263bbda1d5c397d31601566ed6571c33b2b565.nq.gz
│   └── f0c1ac84a64f29c6b0af412ba2f0f4bc7d55a9e0.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 65e976d66064dbdd498e29715578b1e5fdad43d5.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 22 files
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

[alexmojaki/sorcery](https://github.com/alexmojaki/sorcery)

---
*Parsed on 2026-10-19 by [repolex](https://repolex.ai)*
