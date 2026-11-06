# Repolex Knowledge Graph of sphinx-contrib/svgbob

RDF knowledge graph data for [sphinx-contrib/svgbob](https://github.com/sphinx-contrib/svgbob), parsed by [repolex](https://repolex.ai).

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
rlex download sphinx-contrib/svgbob
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 039500b61eca6ad7209c13b30cd777ab7c69447f
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 039500b61eca6ad7209c13b30cd777ab7c69447f
│           └── chunk-001.nq.gz
├── blob
│   ├── 03a466a70991ed0ea5eb3ea99925c90d5733274e.nq.gz
│   ├── 0d9cc590121d63782efffbc4b8a9cd6b8331902c.nq.gz
│   ├── 14cf95e24b1d2e7f564103488a2c123bc2b8dbda.nq.gz
│   ├── 23be0c2bf54aa7edb332ed6e6873477a09428115.nq.gz
│   ├── 2fe3b4e7b868a1a59d39692df058e2ab0f506ee4.nq.gz
│   ├── 33433850098af5fc43ccb192571ccfaab3fd0bd4.nq.gz
│   ├── 361f4d4d79b761d98d8f3ce1cddd15ab09ca5a3c.nq.gz
│   ├── 3aa479d3a60ce44b45409d8f3088896d9732f85c.nq.gz
│   ├── 3f672480b65e03fe691f02e5ed3eadb4d709bf9b.nq.gz
│   ├── 4a0de69e6cbe7454f6fafaf0e0f020230819a583.nq.gz
│   ├── 4b019515ef5ef5c22a5e4d3fb86782f743d3b300.nq.gz
│   ├── 60802cfe81994828c65b3e32a0014b551593e33e.nq.gz
│   ├── 64efeb17fc5d2db30261846994bbffc20505c281.nq.gz
│   ├── 6aaf4e9a1dabb79b3cd6d1316bb78344d3f86e91.nq.gz
│   ├── 6dc09726bee65b13801c7937ea6ef85cb430500d.nq.gz
│   ├── 837881e419b61431c19c2cdfa2866fa35b178377.nq.gz
│   ├── 88f88989c1d255300cbc6650e17be5d9527281d2.nq.gz
│   ├── 8a33348c7d811afb28795f9d529a9d96e6762eaf.nq.gz
│   ├── 989e5f1fada02257cc9ced49eeeb582645a93bad.nq.gz
│   ├── a22b7ebcc6ece51ca0752010de781473ced9c8f5.nq.gz
│   ├── b2528f238060653ce389d84853d85d1333173bd8.nq.gz
│   ├── c29ee2e59f262a756a2118d4c4fb7b851c040218.nq.gz
│   ├── d09f20553d84e522fda6aa94612a49cfa2239d1b.nq.gz
│   ├── d8cb4e01dc766eb0a76a625c2daee7f26e89a27d.nq.gz
│   ├── dfaf998906cbb10f1f4ed0a033372a05faa2ab5a.nq.gz
│   ├── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
│   ├── e77c579c32de04b561b193d80e335d756f839412.nq.gz
│   ├── f07263087044ed5ac01dbe97405b2772ef32c892.nq.gz
│   ├── f74cb9f74b3ef019eec7a628e43a08726c342543.nq.gz
│   └── fceabc7ccc349c163da29430c047c7f3ce9f9f9c.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 039500b61eca6ad7209c13b30cd777ab7c69447f.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 38 files
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

[sphinx-contrib/svgbob](https://github.com/sphinx-contrib/svgbob)

---
*Parsed on 2026-11-06 by [repolex](https://repolex.ai)*
