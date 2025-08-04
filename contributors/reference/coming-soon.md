---
description: Integrating with the platform vs. building on the platform
---

# Contributor API

## Contributor API vs Developer API

We make a clear distinction between the **Developer** API and the **Contributor** API, because it clarifies a fundamental difference in audience and purpose:&#x20;

* Developer APIs focus on consumption and integration patterns, emphasizing stability, usability, and external use cases
* Contributor APIs document implementation details, internal architecture decisions, and modification workflows that enable effective contribution to the codebase.&#x20;

Clearly, every software system has a "Contributor API", so it is unfortunate there is no standard industry term for this. The term "Contributor API" is especially well-suited to an open-source context where internal team members are indeed contributors, and the term aligns perfectly with established terminology for collaboration in both public and private GitHub repositories.

By adopting this convention, we make it immediately clear whether documentation is intended for those _integrating with_ the system versus those _building on_ the system. In turn, this helps reduce confusion and ensures contributors can easily locate the technical depth they need for internal development work.



<table data-view="cards"><thead><tr><th></th><th></th><th data-hidden data-card-target data-type="content-ref"></th></tr></thead><tbody><tr><td><strong>Contributor API</strong></td><td>Internal interface for team members modifying and maintaining the system</td><td><a href="https://dev-hub.shiftiq.com/contributor/index.html">https://dev-hub.shiftiq.com/contributor/index.html</a></td></tr><tr><td><strong>Developer API</strong></td><td>External public interface for developers and integrators extending the system</td><td><a href="https://docs.shiftiq.com/developers/api-v2/introduction">https://docs.shiftiq.com/developers/api-v2/introduction</a></td></tr></tbody></table>

