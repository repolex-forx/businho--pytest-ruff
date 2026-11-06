# Repolex Knowledge Graph of businho/pytest-ruff

RDF knowledge graph data for [businho/pytest-ruff](https://github.com/businho/pytest-ruff), parsed by [repolex](https://repolex.ai).

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
rlex download businho/pytest-ruff
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── eb815de1fc32dc98d538f7475f3a4dbb22913a8d
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── eb815de1fc32dc98d538f7475f3a4dbb22913a8d
│           └── chunk-001.nq.gz
├── blob
│   ├── 0ed13cf1822af57f59a0463e704319cb283a4f54.nq.gz
│   ├── 1c439c7881862be161c36af5709683eda553c42b.nq.gz
│   ├── 21b405d8c2dac873e9063b1dff87e46c3876aa58.nq.gz
│   ├── 235d42fdd11be48dc984ee54c230467ad00dc6aa.nq.gz
│   ├── 25ab8847adef08dc37402fa36fac8eed5029ca98.nq.gz
│   ├── 31eb0e478e22fdaeb365ff05c5425998059531a8.nq.gz
│   ├── a3b235f365d75cbc4c4ff1671a91ff963c648e86.nq.gz
│   ├── ab9f839f006ff2700cadda325646b85e520eb440.nq.gz
│   ├── b937ba6ac58279d3478a680b3cb7c1db28838731.nq.gz
│   ├── bc6429c31164024f65d6ca9e8d3fa2f4ea0e694a.nq.gz
│   ├── bf100e0c4d4c674532c28bfa5e1b183fd41d9282.nq.gz
│   ├── d73ed1e82bffacb1e92e73390e11725ba24c141e.nq.gz
│   ├── dcf7f74bac3665031897bac8ef9a21f14cd7d8c9.nq.gz
│   ├── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
│   ├── efee0ea3731fb6f1041aa30f76f1bc3cb2748ef2.nq.gz
│   ├── f8a6f7cee41cb6c4686230a437f5cc893a854e6d.nq.gz
│   └── fd12abc09944533b51000ff38b2a2fafa891ff97.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── eb815de1fc32dc98d538f7475f3a4dbb22913a8d.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 25 files
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

[businho/pytest-ruff](https://github.com/businho/pytest-ruff)

---
*Parsed on 2026-11-06 by [repolex](https://repolex.ai)*
