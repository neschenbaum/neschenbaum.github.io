---
layout: page
title: Pricing in a Digital World
description: SNSF funded theoretical and experimental work on dynamic pricing when a firm tracks customers' purchases
img: /assets/img/multi-2.png
importance: 1
category: work
---


Cookies, loyalty cards, or digital fingerprints – companies increasingly make use of the tools digitization provides to study the purchase behavior of their customers and adjust their prices dynamically. This research project provides new insights into optimal pricing when sellers can observe their customers’ purchase histories. This project has been funded by the Swiss National Science Foundation (SNSF), grant no. 178836.

In the first part of the project in <a href="https://neschenbaum.github.io/assets/pdf/escalating-prices-and-fines.pdf">Buehler & Eschenbaum (2020)</a>, we developed the theoretical tools to analyze dynamic monopoly pricing and noted an interesting connection to the literature on optimal law enforcement: conditioning price on customer purchase history is equivalent to conditioning fines on past offenses.

<div class="row justify-content-sm-center">
    <div class="col-sm-8 mt-3 mt-md-0">
      <p>We developed a simple framework to nest monopoly pricing and optimal law enforcement and examine how escalating fines (i.e. fines increasing in the number of previous offenses) arise naturally when the principal gives less than full weight to agent benefits in the maximization problem. Counter-intuitively, escalating fines are driven by decreasing fines for previous non-offenders, because this incentivizes individuals to delay their offense. Our analysis clarifies why the literature has struggled with explaining escalation despite its incredibly widespread adoption in practice.</p>
    </div>
    <div class="col-sm-4 mt-3 mt-md-0">
        <img class="img-fluid rounded z-depth-1" src="{{ '/assets/img/escalating-period1.png' | relative_url }}" alt="" title="First period behavior for a linear distribution function"/>
    </div>
</div>

The main part of the project takes the lessons learned in the first paper and develops a unifying monopoly pricing framework with two varieties on offer in <a href="https://neschenbaum.github.io/assets/pdf/Multiproduct_Dynamic_Pricing.pdf">Buehler & Eschenbaum (2021)</a>. We allow for varieties to be sold as a durable or a rental, and arbitrary correlations between consumers' values for the varieties.

<div class="row justify-content-sm-center">
    <div class="col-sm-7 mt-3 mt-md-0">
      <p>The game revolves around three states (the two varieties and the outside option), and admissible transitions between these states. All consumers begin the game in the same state and can choose to transition between them each period according to the admissible transitions. The seller can condition the price charged on the observed history of choices for each consumer, but if a consumer cannot refuse to purchase (transition to the outside option), we impose a price of zero.</p>
    </div>
    <div class="col-sm-5 mt-3 mt-md-0">
        <img class="img-fluid rounded z-depth-1" src="{{ '/assets/img/multi-statemachine.png' | relative_url }}" alt="" title="Finite state machine for two rental varieties"/>
    </div>
</div>

We focus on a concept we call 'trading up'. It is meant to capture the simple idea that a seller has an incentive to try to induce a customer to purchase a good the customer is willing to pay more for relative to the previously chosen purchase (or non-purchase) option, i.e. to trade the customer up to a more valuable option. For example, airlines offer upgrades to business class for reduced prices to economy passengers; supermarkets send coupons with price reductions for a higher-priced alternative to something bought previously; insurance companies offer lower rates for new customers than old; etc. We show that trading up drives dynamic pricing in repeated monopoly problems and extends the logic of Coasian dynamics.

Our analysis shows that if the demand function is known to the seller (so that there is no statistical learning problem), and the state of the world is constant, then the only reason to dynamically price is because the consumers previous choice reveals something about their willingness-to-pay and exploiting this is valuable to the seller: inducing a customer to pick a more valuable option increases the total surplus available in trade and thus the seller can obtain a higher profit when trading up. So this form of dynamic pricing could also be interpreted as 'dynamic market segmentation' of a fix and known demand function.

We then take our framework to the lab to observe how individuals actually behave in dynamic monopoly pricing settings. We match one consumer to one seller and study pricing dynamics that arise when sellers and buyers interact repeatedly and how this compares to the theoretic predictions. We differentiate between durable and rental goods on offer and whether the seller is able to commit to prices ex-ante or not. This work is ongoing.

<h4>Project materials:</h4><ul><li>
<a href="https://stefan-buehler.net">Stefan Buehler</a> and Nicolas Eschenbaum. <a href="/assets/pdf/escalating-fines-and-prices.pdf">Explaining Escalating Fines and Prices: A Unified Approach</a>. <i>Journal of Economic Behavior and Organization.</i> Volume 171, March 2020, Pages 153-164.
</li>
<li>
<a href="https://stefan-buehler.net">Stefan Buehler</a> and Nicolas Eschenbaum. <a href="/assets/pdf/Multiproduct_Dynamic_Pricing.pdf">Dynamic Monopoly Pricing With Multiple Varieties: Trading Up</a> (WP). <i>2021.</i>
</li>
</ul>
