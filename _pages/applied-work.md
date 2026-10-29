---
layout: page
permalink: /applied-work/
title: Applied Work
description: Selected advisory, applied, and policy-research projects — competition cases, policy and regulation, energy markets, and mechanism design.
nav: true
nav_order: 3
---

<p class="aw-intro">
  I work as an economic expert in competition proceedings and advise public bodies on algorithmic pricing, digital markets, energy, and AI
  regulation, mainly in Switzerland and the EU, in English and German. Engagements run through Swiss Economics; contact me at
  <a href="mailto:{{ 'nicolas.eschenbaum@swiss-economics.ch' | encode_email }}">nicolas.eschenbaum [at] swiss-economics.ch</a>.
</p>

<h2 class="aw-group">Competition cases</h2>
<div class="applied-work">
  <div class="aw-item">
    <div class="aw-year">2022 – present</div>
    <div class="aw-desc">Expert reports and economic analysis for parties in proceedings before the Swiss Competition Commission (WEKO) involving information exchange and cartel allegations, including in the retail sector.</div>
  </div>
  <div class="aw-item">
    <div class="aw-year">2023 – 2025</div>
    <div class="aw-desc">Lead economic analysis for a car-finance provider in WEKO cartel proceedings concerning interest rates.</div>
  </div>
  <div class="aw-item">
    <div class="aw-year">2024 – 2025</div>
    <div class="aw-desc">Market definition and competitive assessment for a major digital platform.</div>
  </div>
  <div class="aw-item">
    <div class="aw-year">2023</div>
    <div class="aw-desc">Consulted on pricing algorithms for the market-definition work in the review of a major cross-border merger.</div>
  </div>
</div>

<h2 class="aw-group">Policy and regulation</h2>
<div class="applied-work">
  <div class="aw-item">
    <div class="aw-year">2026 – present</div>
    <div class="aw-desc">Study on modern pricing methods, pricing algorithms, and risks of collusion for the European Commission (DG COMP). I lead the competition-economics analysis, in particular on third-party algorithmic pricing; Swiss Economics is the only competition-economics consultancy in the consortium.</div>
  </div>
  <div class="aw-item">
    <div class="aw-year">2025 – present</div>
    <div class="aw-desc">Regulatory impact assessment of intellectual-property rules for AI systems, for the Swiss Federal Institute of Intellectual Property (IPI).</div>
  </div>
  <div class="aw-item">
    <div class="aw-year">2024 – 2025</div>
    <div class="aw-desc"><a href="{{ '/applied-work/foundation-models-switching-costs/' | relative_url }}">Market power and switching costs in the foundation-models market</a> — enterprise survey and analysis, European AI &amp; Society Fund Global Fellowship.</div>
  </div>
</div>

<h2 class="aw-group">Energy markets</h2>
<div class="applied-work">
  <div class="aw-item">
    <div class="aw-year">2024 – 2025</div>
    <div class="aw-desc">Bidding and coordination analysis in secondary reserve-power markets.</div>
  </div>
  <div class="aw-item">
    <div class="aw-year">2024 – 2025</div>
    <div class="aw-desc">Assessment of reserve-power requirements in Switzerland and neighbouring countries, for the Federal Electricity Commission (ElCom).</div>
  </div>
  <div class="aw-item">
    <div class="aw-year">2023 – 2025</div>
    <div class="aw-desc">Market-power analysis for energy trading platforms using multi-agent deep reinforcement learning — ChartEP project, Swiss Federal Office of Energy (SFOE).</div>
  </div>
  <div class="aw-item">
    <div class="aw-year">2023 – 2024</div>
    <div class="aw-desc">Price-elasticity estimation in German wholesale and end-user energy markets — <a href="https://www.seco.admin.ch/seco/de/home/Publikationen_Dienstleistungen/Publikationen_und_Formulare/Strukturwandel_Wachstum/Branchenanalysen/wp_47.html"><em>Wirtschaftspolitik</em> Nr.&nbsp;47</a>, State Secretariat for Economic Affairs (SECO).</div>
  </div>
</div>

<h2 class="aw-group">Mechanism design</h2>
<div class="applied-work">
  <div class="aw-item">
    <div class="aw-year">2023 – 2024</div>
    <div class="aw-desc">Incentive analysis and mechanism design for a Web3 platform.</div>
  </div>
  <div class="aw-item">
    <div class="aw-year">2024</div>
    <div class="aw-desc">Game-theoretic and agent-based analysis of issuance-curve effects on staking behaviour.</div>
  </div>
</div>

<p class="aw-disclosure">
  Disclosure: Through Swiss Economics I advise competition authorities and private parties, including firms active in digital markets.
  Research funding is listed on my <a href="{{ '/cv/' | relative_url }}">CV</a>.
</p>

<style>
  .aw-intro {
    margin-top: 1rem;
  }
  .aw-group {
    font-size: 0.95rem;
    font-weight: 600;
    letter-spacing: 0.06em;
    text-transform: uppercase;
    color: var(--global-text-color-light);
    margin: 2.25rem 0 0.6rem;
  }
  .aw-disclosure {
    margin-top: 2rem;
    font-size: 0.9rem;
    color: var(--global-text-color-light);
  }
  .aw-item {
    display: flex;
    flex-direction: row;
    gap: 1.5rem;
    padding: 0.9rem 0;
    border-top: 1px solid var(--global-divider-color);
  }
  .aw-item:last-child {
    border-bottom: 1px solid var(--global-divider-color);
  }
  .aw-year {
    flex: 0 0 8rem;
    color: var(--global-theme-color);
    font-weight: 600;
    font-size: 0.9rem;
    padding-top: 0.1rem;
  }
  .aw-desc {
    flex: 1 1 auto;
  }
  @media (max-width: 576px) {
    .aw-item {
      flex-direction: column;
      gap: 0.2rem;
    }
    .aw-year {
      flex-basis: auto;
    }
  }
</style>
