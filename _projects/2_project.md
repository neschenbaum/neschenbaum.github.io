---
layout: page
title: Computational Learning in Games
description: U of St. Gallen and Hasler Foundation funded work on RL in economic games
img: /assets/img/algos-2.png
importance: 2
category: research
---


Companies increasingly employ machine learning techniques in their decision-making. In digital markets in particular, such algorithms are a key factor in ensuring a firm's success. But despite their widespread adoption, we know very little about how algorithms interact and how they can influence economic outcomes. In this project, we investigate the behavior of interacting reinforcement learning algorithms in standard economic games and develop a software environment in which the behavior of learners in mathematical games can be studied.
<!---The classic economic approach to settings with strategic interdependence is based on game theory. This requires building a model of the game, solving for its equilibrium, and then analyzing the equilibrium properties. But this necessitates an emphasis on model tractability and directly conflicts with the complexity and ‘black-box’ nature of reinforcement learning processes. In addition, little to no empirical evidence on the behavior of algorithms in markets or antitrust cases exist. How big of a concern the use of learning software is in practice is thus difficult to ascertain.
--->

Funding by the University of St. Gallens Basic Research Fund allowed us to lay the groundwork by implementing simple Q-learning algorithms in repeated pricing games with imperfect competition. In <a href="https://neschenbaum.github.io/assets/pdf/robust-algorithmic-collusion.pdf">Eschenbaum et al. (2021)</a>, we apply our software to study the ability of learners to tacitly collude in Bertrand-style games. A recent literature finds that algorithms consistently learn to collude, however existing work reports results solely based on performance in the training environment. In practice, firms train their algorithms offline before using them, and the training and market environment differ. To study the possibility for learners to extrapolate collusive policies to the market environment, we develop a formal, general framework to guide the analysis of reinforcement learners in economic games.

We first show that while algorithmic collusion consistently arises during training, in testing contexts collusion vanishes. This does not change with further iterations. Instead, we observe evidence of Nash play of the underlying stage game. This shows that algorithmic collusion is not robust to changes in the environment, and performance during training is no indication of outcome in the market.

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        <img class="img-fluid rounded z-depth-1" src="{{ '/assets/img/algos-main-result.png' | relative_url }}" alt="" title="Profits in training vs testing contexts"/>
    </div>
    <div class="col-sm mt-3 mt-md-0">
        <img class="img-fluid rounded z-depth-1" src="{{ '/assets/img/algos-transitive-closure-1.png' | relative_url }}" alt="" title="An example of a strategy pair"/>
    </div>
</div>
<div class="caption">
    On the left, average profits measured using a collusion index in training and testing contexts. On the right, the transitive closure of a strategy pair after convergence during training. Source: <a href="https://neschenbaum.github.io/assets/pdf/robust-algorithmic-collusion.pdf">Eschenbaum et al. (2021)</a>.
</div>

 It turns out that the reason for this breakdown of collusion is an overfitting to rival strategies from training, and more broadly the high-dimensionality of the strategy space. Even pairs of jointly converged policies that lead to the same collusive outcome during training can be vastly different, and all generally have multiple different stable outcomes that can be played. It is unsurprising that a given policy learnt during training then does not lead to the same outcome when playing against a policy different to the rival policy from training.

<div class="row justify-content-sm-center">
    <div class="col-sm-6">
        As a consequence, we further show that restricting algorithms' strategy space can solve this problem and make algorithmic collusion robust. Outcomes during training and testing now become indistinguishable, and for part of the space of parameters that we consider, we obtain collusive outcomes. The restriction on the strategy space can make algorithmic collusion robust, because it forces algorithms to learn collusive policies based on simpler patterns that are not too specific to the training context and can thus be extrapolated.
    </div>
    <div class="col-sm-6 mt-3 mt-md-0">
        <img class="img-fluid rounded z-depth-1" src="{{ '/assets/img/algos-restrict-result.png' | relative_url }}" alt="" title="Profits when the strategy space is restricted"/>
    </div>
</div>



Our analysis suggests that a key driving force of algorithmic collusion in practice is coordination of algorithm *design*. Firms in practice may be able to successfully achieve algorithmic (tacit) collusion by coordinating on high-level ideas for the implementation of learning algorithms.
<!---Each firm then implements and trains its algorithm independently. Yet by choosing the parameterization of the environment, and the observation and thus policy space appropriately, collusive policies can be made sufficiently robust to extrapolate to the market. Intuitively, precisely because the degree of coordination among competing firms is (legally) restricted, and algorithms must potentially work in a range of environments, the policy employed must rely on simpler patterns and cannot be too specific.--->

Further funding by the Hasler Foundation has allowed us to develop a comprehensive integration of game theory and machine learning. We have integrated a programmatic, modular framework of mathematical games called open games with machine learning libraries, in particular Ray and Rlib. The repository for open games can be found <a href="https://github.com/philipp-zahn/open-games-hs">here</a>, for the underlying re-development of game theory called compositional game theory see <a href="https://arxiv.org/abs/1603.04641">Ghani et al, 2018</a>. This software allows a modular construction and combination of complex games with separately scripted cutting-edge RL algorithms.


<h4>Project materials:</h4><ul><li>
Nicolas Eschenbaum, Filip Mellgren, and Philipp Zahn. <a href="/assets/pdf/robust-algorithmic-collusion.pdf">Robust Algorithmic Collusion</a> (WP). <i> 2021.</i>
</li>
</ul>
