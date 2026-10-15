# Repolex Knowledge Graph of sphinx-contrib/email

RDF knowledge graph data for [sphinx-contrib/email](https://github.com/sphinx-contrib/email), parsed by [repolex](https://repolex.ai).

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
rlex download sphinx-contrib/email
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── e23db323d1ac20ecd7585df140eaa4d05ea70a5b
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── e23db323d1ac20ecd7585df140eaa4d05ea70a5b
│           └── chunk-001.nq.gz
├── blob
│   ├── 042c8f79713c19ade417cf69f0451e6066d6c6af.nq.gz
│   ├── 2bec4803c4bdca67d49f2dcb974faae129d6549a.nq.gz
│   ├── 31b59ff474b5f70949547653c5a9fafc0b917a8f.nq.gz
│   ├── 416634f5288f7f60a9b9f68eb63afd0bed3443a2.nq.gz
│   ├── 4fdfbbbaa1d6f03412fd345906bcc821ad6b795c.nq.gz
│   ├── 551e212a7d54407a9c99cddbdba4201935a461fa.nq.gz
│   ├── 6f7a2c15e2ea46e03b6863906714bf3457bf50ae.nq.gz
│   ├── 707a001a832e364b9dbacf109ee3a140aae9a2ec.nq.gz
│   ├── 810bac799ff3838bedc710e2a223d5743f845e50.nq.gz
│   ├── 8917a484e116cfb558c151c2c54d3f3fc7332abc.nq.gz
│   ├── 91005ad6084bbf2705ef63fb799bdc8303a86a9b.nq.gz
│   ├── 945e941393e42ba377317c200478b5e61f531042.nq.gz
│   ├── 99755ed3fe41ab293379c7d84a288c31bb156c11.nq.gz
│   ├── 9f428d766b8c012937da20735e5f39e75d980c48.nq.gz
│   ├── a7339aefb4ddf160758bd32ba3b879d1cc7ee3b7.nq.gz
│   ├── c0f62de6c4377875191d25b52d1ee6d564477d4f.nq.gz
│   ├── ca09957ff9b9fb463660290cdadd219219ae6e9c.nq.gz
│   ├── ca52345562689867d4d9de2206d12725af37a345.nq.gz
│   └── e67ba6a139aaa5f024ebd3a1527eec6a67528eca.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── e23db323d1ac20ecd7585df140eaa4d05ea70a5b.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 27 files
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

[sphinx-contrib/email](https://github.com/sphinx-contrib/email)

---
*Parsed on 2026-10-15 by [repolex](https://repolex.ai)*
