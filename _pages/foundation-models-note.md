---
layout: distill
title: "Market Power and Switching Costs in the Foundation Models Market: Evidence from a Developer Survey"
description: Exploratory evidence from a survey of 19 organizations with production AI deployments — provider choices, switching costs, and lock-in.
date: 2026-01-30
permalink: /applied-work/foundation-models-switching-costs/
nav: false

authors:
  - name: Nicolas Eschenbaum
    url: "https://neschenbaum.github.io/"
    affiliations:
      name: Swiss Economics · European AI &amp; Society Fund Global Fellowship

toc:
  - name: Summary
  - name: 1. Introduction
  - name: 2. Data and Method
  - name: 3. Market Structure and Provider Adoption
  - name: 4. Use Case Complexity and Architecture
  - name: 5. Switching Costs
  - name: 6. Compliance and Regulated Verticals
  - name: 7. Routing Layers, Commercial Terms, and Trends
  - name: 8. Discussion
  - name: 9. Limitations and Future Research
  - name: 10. Conclusion
  - name: References
---

_Research note based on work carried out under the European AI &amp; Society Fund Global Fellowship Programme on AI &amp; Market Power. The evidence comes from a small survey and is exploratory._

## Summary

The foundation models market has grown very rapidly, and competition authorities have begun to ask whether customers face lock-in despite widespread API standardization. This note reports exploratory evidence from a survey of 19 organizations with production AI deployments, covering provider choices, switching costs, and contractual arrangements. Two providers, Anthropic and OpenAI, are used far more than any other in the sample. Switching costs scale with system complexity: simple use cases can be moved in hours to days, while complex pipelines take weeks or are reported as not feasible. Regulated industries, particularly healthcare, report the highest barriers, driven by compliance requirements rather than technical factors. Routing layers reduce cost differences across providers but not quality differences. Given the small, self-selected sample, the findings are exploratory.

## 1. Introduction

The foundation models market has emerged as one of the fastest-scaling software categories, with enterprise spending reaching an estimated \$37 billion in 2025 (Menlo Ventures, 2025). This expansion has attracted scrutiny from competition authorities concerned about market power and customer dependencies in critical AI infrastructure.

Despite widespread API standardization and the emergence of routing and gateway layers, questions persist about the extent to which customers face lock-in. The tension is relevant for policy: if switching costs are low, market concentration may reflect efficient competition and quality differentiation rather than anticompetitive conduct; if switching costs are high, concentration combined with lock-in could warrant closer attention under competition law.

This note investigates four questions:

1. What is the current distribution of provider adoption in production deployments, and how does it vary across use cases?
2. How do switching costs vary by use case complexity, organization size, and industry vertical?
3. What commercial terms, technical dependencies, and compliance requirements correlate with barriers to switching?
4. How effectively do architectural choices such as routing layers reduce provider dependencies?

The analysis draws on the switching costs literature (Klemperer, 1987; Farrell &amp; Shapiro, 1988), work on two-sided platform competition (Rochet &amp; Tirole, 2003; Armstrong, 2006), and the treatment of compliance requirements as barriers to entry (Stigler, 1971; Rey &amp; Tirole, 2007).

## 2. Data and Method

We developed a 46-question structured survey administered online between September and November 2025. It captured organization characteristics, provider and framework adoption, system complexity, switching costs, commercial arrangements, and cost and quality trends over the preceding 6–12 months. Respondents were recruited through professional networks in European AI development communities, with emphasis on production deployments rather than pilots.

The sample is 19 organizations, spread across firm sizes from 1–49 to 10,000+ employees. Respondents were CTOs or CIOs (42%), product leaders (47%), and engineering leads (11%). The sample emphasizes EU and GDPR-regulated organizations, reflecting the fellowship's focus.

Given the sample size, we use descriptive statistics and cross-tabulation rather than inferential tests, and we avoid causal language throughout. Several limitations should be kept in mind from the outset and are returned to in Section 9:

- **Sample size.** n=19 is too small for statistical inference; effect sizes are reported without significance tests.
- **Selection bias.** Organizations willing to discuss dependencies may differ from those that are not; recruitment through professional networks may oversample sophisticated users.
- **Self-reported data.** Switching-cost estimates are hypothetical rather than revealed preferences, and ex ante estimates typically underestimate ex post costs.
- **Cross-sectional design.** The data cannot separate selection effects from treatment effects and does not support causal claims.
- **Geographic skew.** The EU and GDPR focus may overstate compliance barriers relative to the global market.

## 3. Market Structure and Provider Adoption

Respondents could select multiple providers, so adoption rates are reported as the share of organizations using each provider and do not sum to 100%.

- **Anthropic (Claude):** 47% of organizations (9/19)
- **OpenAI (GPT API):** 42% (8/19)
- **Azure OpenAI Service:** 21% (4/19)
- **Google (Gemini):** 16% (3/19)
- **Open-source (self-hosted):** 16% (3/19)
- **Mistral AI:** 11% (2/19)
- **xAI (Grok):** 5% (1/19)

Anthropic and OpenAI are used far more than any other provider, and nearly every organization uses at least one of the two. These sample shares are broadly in line with the Menlo Ventures (2025) enterprise report, which finds Anthropic at 40% of LLM API spend and OpenAI at 27%; the somewhat higher OpenAI share here may reflect sample composition.

Despite this concentration, **68% of organizations (13/19) use multiple providers.** Multi-homing is more common among larger organizations: 60% of large enterprises (10,000+ employees) use three or more providers, against 25% of startups. The 32% that use a single provider are concentrated in regulated industries, in enterprise agreements with cloud bundling, and in smaller organizations with limited resources.

Adoption also varies by use case. Healthcare respondents (3/3) use Anthropic exclusively; coding respondents lean toward OpenAI and Azure OpenAI; content generation is more evenly split across providers. With only a handful of organizations per vertical these differences are indicative rather than precise, but they suggest that a single horizontal "foundation models market" may obscure meaningful variation across use cases.

## 4. Use Case Complexity and Architecture

Organizations report varying ratios of simple atomic queries to complex multi-step pipelines. A high share of simple queries (75–100%) concentrates in coding and content generation, where models provide copilot-style assistance, while healthcare and legal applications skew toward complex pipelines requiring retrieval, tool use, and multi-step reasoning.

**84% of organizations (16/19) operate at least one complex pipeline**; only 16% use exclusively simple API calls. Among the 16 with complex systems, the most common components are embedders (81%), chunking (75%), and vector databases (75%) — the combination of retrieval-augmented generation, which appears in 75% of complex pipelines. Planner or agent components are less common (38%), and only one organization describes the planning-execution-observation loops characteristic of autonomous agents. This is consistent with the Menlo Ventures (2025) finding that a small minority of enterprise deployments qualify as true agents. Production systems favor established retrieval patterns over cutting-edge agentic architectures.

## 5. Switching Costs

**Simple use cases** can generally be moved between providers, but with real friction. The median estimate is 3–8 hours (32% of organizations), with 26% reporting 2–7 days and 16% reporting switching as not feasible.

**Complex pipelines** are markedly harder. Among the 16 organizations with complex systems, the median estimate is 2–7 days (31%), and **25% (4/16) report switching as not feasible.** A further 25% estimate one to four weeks.

Even where switching is feasible, it requires substantial re-engineering. Among organizations with complex pipelines, the median estimate is that 21–50% of prompts require rewriting when changing providers, indicating that prompt engineering is highly provider-specific rather than interchangeable.

Asked where switching hurts most for complex pipelines, respondents point to prompt templates (44%), evaluation harnesses (38%), governance sign-off (31%), tool-calling APIs (25%), and response schemas (19%). Technical debt from prompt optimization and evaluation infrastructure is the primary source of friction; governance processes add organizational inertia independent of the technical work. For simple use cases, 37% report no significant blockers, and where barriers exist they stem from compliance and contract terms rather than technical factors.

## 6. Compliance and Regulated Verticals

Compliance requirements produce the sharpest barriers in the sample.

**Healthcare (n=3).** None of the three healthcare respondents report feasible switching; all three use Anthropic exclusively and all three cite HIPAA Business Associate Agreement (BAA) requirements, clinical validation timelines, and governance sign-off as barriers.

> _"HIPAA compliance and BAA requirements make switching providers nearly impossible — clinical validation alone would take months."_

> _"Healthcare compliance and clinical validation create insurmountable barriers — Claude's safety features and HIPAA compliance make it the only viable choice."_

In the sample, only Anthropic and Azure OpenAI offer HIPAA BAAs. Where a compliance certification is a necessary input and only a few providers offer it, it functions as a barrier to entry that concentrates the market independently of technical merit. Whether limited BAA availability reflects genuine compliance costs or avoidable regulatory complexity is an open question that this sample cannot resolve.

**Legal and finance.** One legal respondent uses Google Gemini exclusively because of its long context window, and estimates that switching would require rewriting 51–100% of prompts and chunking strategies that reduce quality. Feature-level differentiation can create quasi-lock-in for use cases where a specific capability is critical, even when switching is technically possible.

**GDPR and self-hosting.** Three organizations (16%) self-host open-source models exclusively, motivated by cost and by EU data-residency requirements:

> _"GDPR requirements mandate EU data residency — self-hosting is only viable option but limits us to open-weight models."_

Data-residency requirements can separate the EU market, where self-hosted and EU-hosted options are favored, from a market where all providers are viable.

## 7. Routing Layers, Commercial Terms, and Trends

**Routing layers.** 32% of organizations (6/19) use routing or gateway layers, and those that do route the majority of their traffic through them, so routers are production infrastructure rather than experiments. Router users report clear benefits: 83% report a 10–50% cost reduction over the past 6–12 months through cost-based routing, and half cite failover and redundancy. But quality parity remains a challenge:

> _"Router helps but quality differences between providers require significant prompt tuning for our sales workflows."_

> _"Multi-provider redundancy is critical for uptime but maintaining quality parity across providers requires constant eval tuning."_

Routers reduce the cost of moving traffic between providers but not the quality differences that remain provider-specific. They ease multi-homing without delivering full substitutability. Router adoption also requires infrastructure investment: no startup in the sample uses one, whereas roughly 40% of larger organizations do.

**Commercial terms.** Most organizations (68%) report no contractual restrictions on switching. Volume commitments (21%) and exclusivity or bundling (16%) concentrate in large enterprises, where 60% face one or the other, against 14% of smaller organizations. Bundling is often tied to cloud commitments:

> _"Enterprise agreement with Microsoft includes bundled Azure credits and unified governance — switching would require renegotiating entire cloud contract."_

**Cost and quality trends.** Over the preceding 6–12 months, 79% of organizations report cost reductions (median 10–50%) and 68% report quality improvements (median 10–50%); none report cost increases or quality declines. Costs falling while quality rises is consistent with active competition on both dimensions, and does not, at least in this window, show incumbents extracting rents from locked-in customers.

## 8. Discussion

The central pattern in the data is an apparent tension: 68% of organizations use multiple providers, which suggests low barriers, yet 84% report that switching an existing deployment would take days to weeks, which suggests high friction.

The resolution is that multi-homing is achieved through parallel deployments for new use cases, not through migration of existing workloads. Organizations add providers for new projects and route new traffic flexibly, but existing pipelines remain provider-specific. As one respondent put it:

> _"We only upgrade models but don't switch them."_

In the terms of the switching-costs literature, the market looks contestable for new deployments — where organizations evaluate several providers and face low switching costs — but exhibits lock-in for existing deployments, where technical debt accumulates and switching costs rise over time. The theory (Klemperer, 1987) predicts aggressive competition for new customers alongside the potential to harvest existing ones. The cost and quality trends here do not show harvesting, which is consistent with a market still in a growth phase and disciplined by entry.

Three observations follow that are relevant for competition analysis, and that a larger study could test:

- **Use case heterogeneity.** Market structure differs enough across use cases that a single horizontal market definition may obscure concentration and lock-in specific to particular verticals such as healthcare.
- **Compliance as a barrier.** Certification requirements such as HIPAA BAAs can concentrate a vertical independently of technical merit, and deserve attention as potential barriers to entry.
- **Routers as a partial constraint.** Routing layers reduce cost differences but not quality differences, so they ease but do not eliminate lock-in; open-source self-hosting is a genuine constraint for cost-sensitive and data-residency-constrained buyers but not for quality-demanding use cases.

## 9. Limitations and Future Research

The sample is small (n=19), self-selected, and skewed toward EU and GDPR-regulated organizations, and the switching-cost figures are self-reported and hypothetical. The findings should therefore be read as exploratory. A larger, stratified survey (n≥100) would permit statistical inference and subgroup analysis; a longitudinal design would allow actual switching events to be observed rather than estimated; and revealed-preference data, for example provider changes in public code repositories, would help validate the self-reported estimates. Vertical deep-dives in healthcare, legal, and finance would be valuable given the heterogeneity across use cases.

## 10. Conclusion

This survey offers early, exploratory evidence on switching costs and market structure in the foundation models market, from organizations with production deployments. Two providers dominate the sample; switching costs rise sharply with system complexity; and compliance requirements create the hardest barriers, particularly in healthcare. Routing layers and open-source alternatives constrain provider power along the cost dimension but not fully along the quality dimension. Taken together, the picture is of early-stage platform competition in which rapidly improving quality and falling costs coexist with emerging sources of lock-in. Whether those dependencies harden into durable market power or erode through better tooling and standardization is an open question that warrants continued empirical work.

## References

Armstrong, M. (2006). Competition in two-sided markets. _RAND Journal of Economics_, 37(3), 668–691.

Farrell, J., &amp; Shapiro, C. (1988). Dynamic competition with switching costs. _RAND Journal of Economics_, 19(1), 123–137.

Klemperer, P. (1987). Markets with consumer switching costs. _Quarterly Journal of Economics_, 102(2), 375–394.

Menlo Ventures (2025). _2025: The State of Generative AI in the Enterprise._

Rey, P., &amp; Tirole, J. (2007). A primer on foreclosure. _Handbook of Industrial Organization_, 3, 2145–2220.

Rochet, J.-C., &amp; Tirole, J. (2003). Platform competition in two-sided markets. _Journal of the European Economic Association_, 1(4), 990–1029.

Stigler, G. J. (1971). The theory of economic regulation. _Bell Journal of Economics and Management Science_, 2(1), 3–21.
