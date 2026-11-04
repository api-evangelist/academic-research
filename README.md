# APIs for Academic Research

**A playbook from [API Evangelist](https://apievangelist.com) and [Ryan Geftman-Gold](https://www.linkedin.com/posts/the-cuny-office-of-research-is-pleased-to-share-7485332341750640641-znak/) for using web APIs to move academic research beyond publication.**

Live at **https://academic-research.apievangelist.com**

Too much university research stops at the journal. This playbook lays out how a research group can turn its data, models and tools into web APIs, so other researchers, companies, developers and communities can use them, and so what they do with it feeds back into the research.

## The five stages

| Stage | The question | What it produces |
|---|---|---|
| **1. Assess** | What do you have, and who could use it? | An inventory, constraints, and likely audiences |
| **2. Pilot** | Can a few trusted users get value from it? | A first API design and a small pilot |
| **3. Scale** | Can many people use it without help? | Docs, onboarding, SDKs, discoverability |
| **4. Sustain** | Can people build on it with confidence? | Plans, licensing, versioning, support |
| **5. Feedback & impact** | What is the world teaching the research? | Usage signals, partnerships, evidence of impact |

The stages connect, and they aren't strictly in order: what you learn at the end loops back to the beginning.

## Fork it

This is a living, forkable playbook. To adapt it for your institution:

1. Fork this repository.
2. Edit `index.html` (the whole playbook is one page) and `_config.yml` (title, description, URL).
3. Change or delete `CNAME`, and turn on GitHub Pages for your fork.

Suggestions and corrections are welcome as issues or pull requests.

## Run it locally

It's a plain Jekyll site:

```
jekyll serve
```

Then open http://localhost:4000. If Bundler complains, run `JEKYLL_NO_BUNDLER_REQUIRE=true jekyll serve`.

## Request an assessment

If your group has research data, content or tools that deserve a wider audience, email [kin@apievangelist.com](mailto:kin@apievangelist.com?subject=Research%20API%20assessment).
