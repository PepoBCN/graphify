# graphify

A [Claude Code](https://claude.com/claude-code) skill that turns any folder of files into a navigable **knowledge graph**.

Point it at a directory of code, docs, research papers, notes or images and it builds:

- an **interactive HTML graph** you can open in a browser, with clustered communities (related things grouped and colour-coded)
- a **GraphRAG-ready JSON** export you can feed into other tools
- a plain-language **`GRAPH_REPORT.md`** that explains what it found, with an honest audit trail of what it could and couldn't link

It's designed to give you the shape of a body of material at a glance, what connects to what, where the clusters are, what's isolated, without you having to read all of it first.

## Install

Drop the skill into your Claude Code skills folder:

```bash
git clone https://github.com/PepoBCN/graphify.git
mkdir -p ~/.claude/skills/graphify
cp graphify/SKILL.md ~/.claude/skills/graphify/SKILL.md
```

(Or just copy `SKILL.md` into `~/.claude/skills/graphify/`.)

Restart Claude Code so it picks up the new skill.

## Use

In any Claude Code session:

```
/graphify
```

Then point it at a folder. Claude reads the files, extracts entities and relationships, runs community detection to find clusters, and writes the three outputs into the working directory.

You can also just describe what you want in plain English, e.g. "graphify this research folder and tell me which papers cluster together".

## What it's good for

- Getting oriented in an unfamiliar codebase or document set
- Mapping a literature review or research corpus
- Spotting hidden connections across notes
- Producing a sharable visual of how a knowledge base hangs together

## How it works

The skill instructs Claude to parse your inputs, build a graph of nodes (entities) and edges (relationships), apply community detection to cluster related nodes, and render it three ways. The **audit trail** is deliberate: rather than inventing links to look impressive, it records what it was confident about and what it wasn't.

## Licence

MIT, see [LICENSE](LICENSE). Use it, fork it, share it.
