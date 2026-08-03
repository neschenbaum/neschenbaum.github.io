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
  - name: 7. Routing, Commercial Terms, and Market Dynamics
  - name: 8. Discussion
  - name: 9. Limitations and Future Research
  - name: 10. Conclusion
  - name: References
---

_Research note based on work carried out under the European AI &amp; Society Fund Global Fellowship Programme on AI &amp; Market Power. The evidence comes from a small survey and is exploratory._

## Summary

The foundation models market has grown very rapidly, and competition authorities have begun to ask whether customers face lock-in despite widespread API standardization. This note reports exploratory evidence from a survey of 19 organizations with production AI deployments, covering provider choices, switching costs, and contractual arrangements. Two providers, Anthropic and OpenAI, are used far more than any other in the sample. Switching costs scale with system complexity: simple use cases can be moved in hours to days, while complex pipelines take weeks or are reported as not feasible. Regulated industries, particularly healthcare, report the highest barriers, driven by compliance requirements rather than technical factors. Routing layers reduce cost differences across providers but not quality differences, and few customers say they would absorb a large price increase without optimizing, routing, or switching traffic. Given the small, self-selected sample, the findings are exploratory.

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

The sample is 19 organizations, spread across firm sizes from 1–49 to 10,000+ employees. Respondents were product leaders (53%), CTOs or CIOs (32%), engineering leads (11%), and one founder/CEO (5%). The sample emphasizes EU and GDPR-regulated organizations, reflecting the fellowship's focus.

Given the sample size, we use descriptive statistics and cross-tabulation rather than inferential tests, and we avoid causal language throughout. Several limitations should be kept in mind from the outset and are returned to in Section 9:

- **Sample size.** n=19 is too small for statistical inference; effect sizes are reported without significance tests.
- **Selection bias.** Organizations willing to discuss dependencies may differ from those that are not; recruitment through professional networks may oversample sophisticated users.
- **Self-reported data.** Switching-cost estimates are hypothetical rather than revealed preferences, and ex ante estimates typically underestimate ex post costs.
- **Cross-sectional design.** The data cannot separate selection effects from treatment effects and does not support causal claims.
- **Geographic skew.** The EU and GDPR focus may overstate compliance barriers relative to the global market.

## 3. Market Structure and Provider Adoption

Respondents could select multiple providers, so adoption rates are reported as the share of organizations using each provider and do not sum to 100%.

<style>
.note-fig { margin: 1.6rem 0; text-align: center; }
.note-fig img { max-width: 100%; height: auto; }
.note-fig .fig-dark { display: none; }
html[data-theme="dark"] .note-fig .fig-light { display: none; }
html[data-theme="dark"] .note-fig .fig-dark { display: inline-block; }
.note-fig-cap { font-size: 0.85rem; color: #828282; margin-top: 0.5rem; }
</style>

<div class="note-fig">
  <img class="fig-light" src="{{ '/assets/img/foundation-models-note/fig1_providers_light.png' | relative_url }}" alt="Provider adoption as a share of the 19 organizations: Anthropic 58%, OpenAI 53%, Google, Azure OpenAI and open-source 21% each, Mistral 16%, xAI 5%." />
  <img class="fig-dark" src="{{ '/assets/img/foundation-models-note/fig1_providers_dark.png' | relative_url }}" alt="Provider adoption as a share of the 19 organizations: Anthropic 58%, OpenAI 53%, Google, Azure OpenAI and open-source 21% each, Mistral 16%, xAI 5%." />
  <div class="note-fig-cap">Provider adoption as a share of organizations (n = 19). Organizations can use more than one provider, so shares do not sum to 100%.</div>
</div>

Anthropic and OpenAI are used far more than any other provider, and nearly every organization uses at least one of the two. These sample shares run above the Menlo Ventures (2025) enterprise report, which finds Anthropic at 40% of LLM API spend and OpenAI at 27%; both providers are higher here, which may reflect the sample's small size and composition.

The more common pattern, though, is concentration on a single provider: **a majority of organizations (58%, 11/19) use just one**, while 42% (8/19) use two or more. Multi-homing rises with organization size — 60% of large enterprises (10,000+ employees) use three or more providers, against one of four startups — and single-provider use is most common in regulated industries, under enterprise agreements with cloud bundling, and among smaller organizations with limited resources.

Adoption also varies by use case. Both healthcare respondents use Anthropic exclusively; coding respondents lean toward OpenAI and Azure OpenAI; content generation is more evenly split across providers. With only a handful of organizations per vertical these differences are indicative rather than precise, but they suggest that a single horizontal "foundation models market" may obscure meaningful variation across use cases.

## 4. Use Case Complexity and Architecture

Organizations report varying ratios of simple atomic queries to complex multi-step pipelines. A high share of simple queries (75–100%) concentrates in coding and content generation, where models provide copilot-style assistance, while healthcare and legal applications skew toward complex pipelines requiring retrieval, tool use, and multi-step reasoning.

**89% of organizations (17/19) operate at least one complex pipeline**; only 11% (2/19) use exclusively simple API calls. Among the 17 with complex systems, the most common components are embedders (76%), chunking (71%), and vector databases (59%) — the combination of retrieval-augmented generation, which appears in 59% (10/17) of complex pipelines. Planner or agent components are less common (24%), and only one organization describes the planning-execution-observation loops characteristic of autonomous agents. This is consistent with the Menlo Ventures (2025) finding that a small minority of enterprise deployments qualify as true agents. Production systems favor established retrieval patterns over cutting-edge agentic architectures. One caveat matters here: the pipelines this survey measures are largely custom-built — bespoke prompt templates, evaluation harnesses, and retrieval stacks assembled in-house — and it was fielded (September–November 2025) just as generic agents such as Claude Code and Codex were beginning to replace some of that custom scaffolding. As they do, the switching costs documented below may migrate — from a team's own pipeline toward the agent and the provider behind it — rather than simply disappear.

## 5. Switching Costs

**Simple use cases** can generally be moved between providers, but with real friction. The median estimate is 3–8 hours (26% of organizations, 5/19), with 21% (4/19) reporting 2–7 days and 16% (3/19) reporting switching as not feasible.

**Complex pipelines** are markedly harder. Among the 17 organizations with complex systems, the median estimate is 2–7 days, and **24% (4/17) report switching as not feasible.** A further 35% (6/17) estimate one to four weeks.

<div class="note-fig">
  <img class="fig-light" src="{{ '/assets/img/foundation-models-note/fig2_switching_light.png' | relative_url }}" alt="Time to switch primary model provider, simple use cases versus complex pipelines. Simple cases cluster at hours; complex pipelines spread into weeks and 'not feasible'." />
  <img class="fig-dark" src="{{ '/assets/img/foundation-models-note/fig2_switching_dark.png' | relative_url }}" alt="Time to switch primary model provider, simple use cases versus complex pipelines. Simple cases cluster at hours; complex pipelines spread into weeks and 'not feasible'." />
  <div class="note-fig-cap">Time to switch primary model provider, by pipeline complexity (number of organizations).</div>
</div>

Time is not the only measure. Asked whether they could switch _without_ substantial application-code changes, most said yes for simple use cases (12 of the 16 who answered) but split evenly for complex pipelines — seven yes, seven no. Beyond atomic calls, changing provider is an engineering project, not a configuration change.

Even where it is feasible, switching means real re-engineering, and the work clusters in the prompt layer. For simple use cases, teams expect to rewrite prompt templates (74%) and response-schema or JSON handling (53%); deeper changes — tool and function adapters, client SDKs, data connectors — are rarer, around one in ten. For complex pipelines the median team expects to rewrite 21–50% of its prompts when changing providers. Prompt engineering is highly provider-specific rather than interchangeable.

Asked where switching hurts most, respondents point to the same two layers — prompt templates and governance sign-off (each cited by nine of nineteen) — followed by evaluation harnesses, tool-calling APIs, and response schemas.

<div class="note-fig">
  <img class="fig-light" src="{{ '/assets/img/foundation-models-note/fig3_switching_pain_light.png' | relative_url }}" alt="Where switching hurts most: prompt templates and governance sign-off (each 47%), evaluation harness 37%, tool-calling APIs 32%, response schema, retrieval stack and compliance certification 21% each." />
  <img class="fig-dark" src="{{ '/assets/img/foundation-models-note/fig3_switching_pain_dark.png' | relative_url }}" alt="Where switching hurts most: prompt templates and governance sign-off (each 47%), evaluation harness 37%, tool-calling APIs 32%, response schema, retrieval stack and compliance certification 21% each." />
  <div class="note-fig-cap">Where switching hurts most (share of respondents; up to three selections each).</div>
</div>

Re-validation compounds the cost: moving a complex pipeline typically means rebuilding the evaluation harness (79%) and re-checking guardrails (47%), retrieval parameters (32%), and tool schemas (26%). The barriers that arise for _simple_ use cases, by contrast, are contractual or compliance-related — contract terms and safety/policy gates (each cited by seven respondents) — rather than technical.

## 6. Compliance and Regulated Verticals

Compliance requirements produce the sharpest barriers in the sample.

**Healthcare (n=2).** Neither healthcare respondent reports feasible switching; both use Anthropic exclusively and both cite HIPAA Business Associate Agreement (BAA) requirements, clinical validation timelines, and governance sign-off as barriers.

> _"HIPAA compliance and BAA requirements make switching providers nearly impossible — clinical validation alone would take months."_

> _"Healthcare compliance and clinical validation create insurmountable barriers — Claude's safety features and HIPAA compliance make it the only viable choice."_

Both healthcare respondents hold a HIPAA BAA, in each case with Anthropic. Where a compliance certification is a necessary input and only a few providers offer it, it functions as a barrier to entry that concentrates the market independently of technical merit. Whether limited BAA availability reflects genuine compliance costs or avoidable regulatory complexity is an open question that this sample cannot resolve.

**Legal and finance.** One legal respondent uses Google Gemini exclusively because of its long context window, and estimates that switching would require rewriting 51–100% of prompts and chunking strategies that reduce quality. Feature-level differentiation can create quasi-lock-in for use cases where a specific capability is critical, even when switching is technically possible.

**GDPR and self-hosting.** Two organizations (11%) self-host open-source models exclusively, motivated by cost and by EU data-residency requirements:

> _"GDPR requirements mandate EU data residency — self-hosting is only viable option but limits us to open-weight models."_

Data-residency requirements can separate the EU market, where self-hosted and EU-hosted options are favored, from a market where all providers are viable.

## 7. Routing, Commercial Terms, and Market Dynamics

**Routing layers.** 32% of organizations (6/19) use routing or gateway layers, and those that do route the majority of their traffic through them, so routers are production infrastructure rather than experiments. Router users report clear benefits: all six report a 10–50% cost reduction over the past 6–12 months through cost-based routing, and four of the six cite fallback and redundancy. But quality parity remains a challenge:

> _"Router helps but quality differences between providers require significant prompt tuning for our sales workflows."_

> _"Multi-provider redundancy is critical for uptime but maintaining quality parity across providers requires constant eval tuning."_

Routers reduce the cost of moving traffic between providers but not the quality differences that remain provider-specific. They ease multi-homing without delivering full substitutability. Router adoption also requires infrastructure investment: no startup in the sample uses one, whereas roughly 40% of larger organizations do.

**Commercial terms.** Most organizations (68%) report no contractual restrictions on switching. Volume commitments (21%) and exclusivity or bundling (16%) concentrate in large enterprises, where four of five (10,000+ employees) face one or the other, against 14% of smaller organizations. Bundling is often tied to cloud commitments:

> _"Enterprise agreement with Microsoft includes bundled Azure credits and unified governance — switching would require renegotiating entire cloud contract."_

**Trends over the past 6–12 months.** Almost all organizations report lower unit costs (18/19, 79% in the 10–50% band) and most report higher quality (15/19, 68% in the band); none report higher costs or lower quality. Other dimensions moved less: latency was mostly flat (58%) or lower, and safety-incident rates were flat or lower. Two trends bear on switching costs directly — 47% report that the _engineering effort_ to change providers has fallen over the year, suggesting tooling is gradually lowering switching costs even as pipelines grow more complex, and router traffic is rising wherever it is measured. Costs falling while quality rises is consistent with active competition, and does not, at least in this window, show incumbents extracting rents from locked-in customers.

**Response to a price increase.** Asked what they would do if their primary provider raised effective prices by 25%, most organizations named responses short of leaving — optimizing usage (42%), routing traffic elsewhere (32%), or renegotiating terms (26%) — while 32% said they would switch their primary provider and only 16% would simply accept the higher cost.

<div class="note-fig">
  <img class="fig-light" src="{{ '/assets/img/foundation-models-note/fig4_price_response_light.png' | relative_url }}" alt="Reported response to a 25% price increase by the primary provider: optimize usage 42%, route traffic elsewhere 32%, switch primary provider 32%, negotiate better terms 26%, accept higher cost 16%, deploy own fine-tuned model 11%." />
  <img class="fig-dark" src="{{ '/assets/img/foundation-models-note/fig4_price_response_dark.png' | relative_url }}" alt="Reported response to a 25% price increase by the primary provider: optimize usage 42%, route traffic elsewhere 32%, switch primary provider 32%, negotiate better terms 26%, accept higher cost 16%, deploy own fine-tuned model 11%." />
  <div class="note-fig-cap">Reported response to a 25% price increase by the primary provider (share of respondents; multiple selections allowed).</div>
</div>

The pattern fits the rest of the survey. Demand is far from captive: few customers would absorb a double-digit price rise outright, and most have at least a partial margin of response. But "switching," here as elsewhere, tends to mean shifting new or marginal traffic rather than migrating an existing complex pipeline — so the discipline this imposes on providers is real but incomplete.

## 8. Discussion

Two facts sit side by side. Switching a simple workload is usually cheap — hours, in most cases — yet a majority of organizations concentrate on a single provider (58%), and 89% run complex pipelines that they expect would take days to weeks to move. Low headline switching costs coexist with real stickiness.

The resolution is that multi-homing, where it occurs (42%), is achieved through parallel deployments for new use cases rather than migration of existing workloads. Organizations add providers for new projects and route new traffic flexibly, but existing pipelines remain provider-specific. As one respondent put it:

> _"We only upgrade models but don't switch them."_

In the terms of the switching-costs literature, the market looks contestable for new deployments — where organizations evaluate several providers and face low switching costs — but exhibits lock-in for existing deployments, where technical debt accumulates and switching costs rise over time. The theory (Klemperer, 1987) predicts aggressive competition for new customers alongside the potential to harvest existing ones. The cost and quality trends here do not show harvesting, which is consistent with a market still in a growth phase and disciplined by entry.

Three observations follow that are relevant for competition analysis, and that a larger study could test:

- **Use case heterogeneity.** Market structure differs enough across use cases that a single horizontal market definition may obscure concentration and lock-in specific to particular verticals such as healthcare.
- **Compliance as a barrier.** Certification requirements such as HIPAA BAAs can concentrate a vertical independently of technical merit, and deserve attention as potential barriers to entry.
- **Routers as a partial constraint.** Routing layers reduce cost differences but not quality differences, so they ease but do not eliminate lock-in; open-source self-hosting is a genuine constraint for cost-sensitive and data-residency-constrained buyers but not for quality-demanding use cases.

## 9. Limitations and Future Research

The sample is small (n=19), self-selected, and skewed toward EU and GDPR-regulated organizations, and the switching-cost figures are self-reported and hypothetical. The findings should therefore be read as exploratory. A larger, stratified survey (n≥100) would permit statistical inference and subgroup analysis; a longitudinal design would allow actual switching events to be observed rather than estimated; and revealed-preference data, for example provider changes in public code repositories, would help validate the self-reported estimates. Vertical deep-dives in healthcare, legal, and finance would be valuable given the heterogeneity across use cases.

## 10. Conclusion

This survey offers early, exploratory evidence on switching costs and market structure in the foundation models market, from organizations with production deployments. Two providers dominate the sample; switching costs rise sharply with system complexity; and compliance requirements create the hardest barriers, particularly in healthcare. Routing layers and open-source alternatives constrain provider power along the cost dimension but not fully along the quality dimension. Taken together, the picture is of early-stage platform competition in which rapidly improving quality and falling costs coexist with emerging sources of lock-in. Whether those dependencies harden into durable market power or erode through better tooling and standardization is an open question that warrants continued empirical work. It is also a moving target in a specific way: the switching costs measured here are those of custom-built pipelines, and generic agents such as Claude Code and Codex have since begun to replace some of that bespoke scaffolding. A follow-up should ask whether that dissolves the lock-in documented here or merely relocates it — from a team's own pipeline to the agent and the provider behind it.

## References

Armstrong, M. (2006). Competition in two-sided markets. _RAND Journal of Economics_, 37(3), 668–691.

Farrell, J., &amp; Shapiro, C. (1988). Dynamic competition with switching costs. _RAND Journal of Economics_, 19(1), 123–137.

Klemperer, P. (1987). Markets with consumer switching costs. _Quarterly Journal of Economics_, 102(2), 375–394.

Menlo Ventures (2025). _2025: The State of Generative AI in the Enterprise._

Rey, P., &amp; Tirole, J. (2007). A primer on foreclosure. _Handbook of Industrial Organization_, 3, 2145–2220.

Rochet, J.-C., &amp; Tirole, J. (2003). Platform competition in two-sided markets. _Journal of the European Economic Association_, 1(4), 990–1029.

Stigler, G. J. (1971). The theory of economic regulation. _Bell Journal of Economics and Management Science_, 2(1), 3–21.
