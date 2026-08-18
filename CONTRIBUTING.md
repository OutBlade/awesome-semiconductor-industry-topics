# Contributing

Thanks for helping improve this list. The goal is a resource where **every link is worth opening**,
so the bar for inclusion is deliberately high.

## What belongs here

This list covers the semiconductor industry with a strong bias toward:

- **Advanced logic** — sub-10 nm process technology, GAA/nanosheet/forksheet/CFET devices,
  backside power delivery, DTCO/STCO.
- **Lithography and patterning** — EUV, High-NA, computational lithography, masks, resists,
  multi-patterning.
- **Process modules** — deposition, etch, CMP, implant, anneal, epitaxy, and the equipment
  that performs them.
- **Metrology, inspection, yield, and test.**
- **Advanced packaging and heterogeneous integration** — 2.5D/3D, hybrid bonding, TSVs, fan-out,
  panel-level, glass substrates, chiplets, and die-to-die interfaces.
- **The software layer** — TCAD, EDA for advanced nodes and 3D, open PDKs, ML for design and
  manufacturing, fab operations and scheduling.
- **The industry layer** — roadmaps, standards, economics, policy, conferences, and education.

## What does not belong here

- **RTL, HDL, and CPU cores.** Excellent material, wrong list — send it to
  [awesome-opensource-hardware](https://github.com/aolofsson/awesome-opensource-hardware) or
  [awesome-hdl](https://github.com/drom/awesome-hdl).
- **Startup directories.** See
  [awesome-semiconductor-startups](https://github.com/aolofsson/awesome-semiconductor-startups).
- **Mature-node-only material.** Great 180 nm analog content belongs elsewhere unless it teaches
  something that generalizes to the leading edge.
- **PCB design, hobby electronics, and maker projects** — with the single exception of the
  DIY fabrication section, which is about actually making transistors.
- **SEO content pages, link farms, affiliate links, and press releases** with no technical content.

## Entry format

One link, one line, one reason:

```markdown
- [Name](https://example.com) — What it is, and why someone would open it. One or two sentences.
```

Rules:

1. **Every entry needs a description.** "Cool tool" is not a description. Say what it does and what
   it is good for. If it is a paper, say what it establishes. If it is a tool, say what you can run.
2. **Prefer primary sources.** A specification, a paper, a vendor technical brief, or a repository
   beats a news article summarizing one. News articles are acceptable when they are the only public
   account of something.
3. **Flag cost and access.** If something is paywalled, requires registration, or is proprietary,
   say so. This list is not open-source-only, but readers should never be surprised by a paywall.
4. **Flag staleness.** If a repository is archived or has not been touched in years but is still
   worth reading, mark it as archived rather than silently listing it as if it were maintained.
5. **No dead links.** Check before you submit.
6. **Keep entries alphabetical or logically ordered** within a subsection where an order already
   exists. Do not append to the bottom of a sorted list.
7. **Avoid duplicates.** Search the file first — many tools legitimately fit two sections, but pick
   the one where a reader would look first, and cross-reference rather than duplicating.

## Adding a new section

If your entry does not fit anywhere, propose a section. Open an issue first describing:

- What the section covers and why the existing sections do not cover it.
- At least three to five entries you would put in it. A section with one link is a bullet, not a
  section.

Remember to add the section to the table of contents.

## Style

- Wrap prose at roughly 100 characters. Tables and long URLs may exceed this.
- Use an em dash (—) between the link and its description.
- American English, sentence case for descriptions.
- Spell out an acronym on first use within a section: "atomic layer deposition (ALD)".
- Node names get the vendor's capitalization: "N2", "18A", "A16", "SF2".
- Avoid superlatives. "The best" is a claim you have to defend; "the reference implementation" is a
  fact.

## Submitting

1. Fork the repository and create a branch.
2. Make your change to `README.md`.
3. Verify your links resolve.
4. Open a pull request describing what you added and why it clears the bar.

Pull requests that add a large number of links at once are welcome, but expect them to take longer
to review — and expect some entries to be cut.

## Reporting problems

Open an issue for:

- **Dead or redirected links** — include the entry and what it should point to, if you know.
- **Factual errors** — especially in the node roadmap tables, which age quickly. Please include a
  source.
- **Projects that have moved, been renamed, or been abandoned.**

Corrections are as valuable as additions. A curated list that quietly rots is worse than no list.
