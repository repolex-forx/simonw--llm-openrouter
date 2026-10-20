# Repolex Knowledge Graph of simonw/llm-openrouter

RDF knowledge graph data for [simonw/llm-openrouter](https://github.com/simonw/llm-openrouter), parsed by [repolex](https://repolex.ai).

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
rlex download simonw/llm-openrouter
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 6de4963a763f4b6625ad883f1d1a6280b12a16dd
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 6de4963a763f4b6625ad883f1d1a6280b12a16dd
│           └── chunk-001.nq.gz
├── blob
│   ├── 0343062ec5c3c46247a8353f9352a3a4724246bf.nq.gz
│   ├── 0ebffaccdcd93a9e1781a60b107fc8bd51e6c423.nq.gz
│   ├── 10737babd393ebf06ca5188da72df43630ddc503.nq.gz
│   ├── 261eeb9e9f8b2b4b0d119366dda99c6fd7d35c64.nq.gz
│   ├── 4b74c60ac5377281f78ac0a6fae82218a9458c2e.nq.gz
│   ├── 5a6a5da1dd63aca82430ac2974d5cfccbb8bfba5.nq.gz
│   ├── 680a31a39eee9bfe03d40b114c4e01053258dc1c.nq.gz
│   ├── 89e9c9a9c5d365fce04cc48b5daf81c6da699d47.nq.gz
│   ├── 9ac7d35b56a7e4f42dd61e6b947717d9296f0e76.nq.gz
│   ├── 9b55ff8ec85c4ffde52ea81b72838ca38a4360ec.nq.gz
│   ├── d0d5ce3ee8fa6494d61b4f902ee7d8de943e1b36.nq.gz
│   ├── d1d4c888b6d56db9ca9903885ea9e0fc07c23985.nq.gz
│   ├── e0438b1dfa11fc2a6b043ead453d397cda939210.nq.gz
│   ├── f8bbcd3e9c21d5f7bccc390e7d3e0e95478b4b5b.nq.gz
│   └── ffe2198ad590aeb2984ba775aa246cd45448d0a2.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 6de4963a763f4b6625ad883f1d1a6280b12a16dd.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 23 files
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

[simonw/llm-openrouter](https://github.com/simonw/llm-openrouter)

---
*Parsed on 2026-10-20 by [repolex](https://repolex.ai)*
