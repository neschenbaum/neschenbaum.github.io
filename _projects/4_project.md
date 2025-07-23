---
layout: page
title: Multi-agent deep hedging for energy assets
description: Extending deep hedging approaches to strategic settings
img: /assets/img/policies-madh.png
redirect:
importance: 3
category: research
---


Hedging models typically treat market prices as exogenous. But in many markets, players' actions move the market price. We extend existing Deep Hedging approaches that have found great success in practical applications to a multi-agent setting and introduce Multi-Agent Deep Hedging to optimize agents' strategies in strategic environments.

We apply this novel architecture to prosumer trading on electricity trading platforms. With the emergence of photovoltaics and batteries, individual consumers are increasingly becoming producers and need to steer their electricity assets. Batteries in particular essentially offer a dynamic hedge against price fluctuations and uncertainty. Using real-world data from publicly available smart meter readings, we study the behaviour of prosumers and analyze the emerging policies.

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        <img class="img-fluid rounded z-depth-1" src="{{ '/assets/img/madh-policies.png' | relative_url }}" alt="" title="Battery charging policies"/>
    </div>
</div>
<div class="caption">
    An example of charging policies for a prosumer. The y-axis shows the PV supply and the x-axis the battery state. Source: <a href="https://neschenbaum.github.io/assets/pdf/madh.pdf">Eschenbaum, Greber & Szehr (2025)</a>.
</div>

We observe economically rational behavior with prosumers charging in the morning (when prices are low), and discharging in the evening (when prices are high). More interestingly, we also see that if the NN has access to the full computation graph and price effects of actions are thus propagated correctly through the network, then agents learn to withhold capacity at the end of the day. This is profitable, because it forces market prices higher on the platform. It shows that allowing algorithms to correctly account for price effects can lead to them learning potentially problematic policies. (But note that in this stylized setting, the market model is encoded and thus the price effects can be cleanly calculated.)

This capacity withholding effect however does not reduce total welfare. Because we allow prosumers to always withdraw the required electricity from the grid instead of the platform total quantity demanded is unchanged. Instead, it represents a redistribution away from prosumers without a battery and towards prosumers with a battery.

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        <img class="img-fluid rounded z-depth-1" src="{{ '/assets/img/madh-learning.png' | relative_url }}" alt="" title="Learning curves"/>
    </div>
</div>
<div class="caption">
    Learning curves for agents with differently sized batteries. The y-axis shows the cost and the x-axis the episode. Source: <a href="https://neschenbaum.github.io/assets/pdf/madh.pdf">Eschenbaum, Greber & Szehr (2025)</a>.
</div>

We show how our MADH approach scales well and is highly practical by running experiments with 32 agents. Agents profiles and demands are built from real-world smart meter data. Learning is consistent and very fast. In further work, we are applying our architecture to study the effects of platform design choices, platform competition, and regulatory policies.

<h4>Project materials:</h4><ul><li>
Nicolas Eschenbaum, Nicolas Greber, and Oleg Szehr. <a href="/assets/pdf/madh.pdf">Multi-Agent Deep Hedging: Benchmarking Prosumer Strategies on Electricity Trading Platforms</a> (WP). <i> 2025.</i>
</li>
</ul>
