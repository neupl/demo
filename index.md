---
layout: default
title: 'NeuPL: Neural Population Learning'
description: 'Learning a population of diverse policies within a single network through self-play.'
---

# NeuPL in a partially-observed, strategy game

In this section we visualize gameplays between 8 distinct policies, represented and executed by a single conditional network. In this experiment, the neural population is learned by implementing `PSRO-Nash`[^1] where incremental policy is optimized to approximately best-respond to the `Nash` mixture over previous policies.

## Training Progression through Time

<p align="center">
  <img src="/assets/img/neupl_rws_progression.gif" />
</p>

## Interactive Viewer of Learned Policies

> * Click on a cell in the payoff matrix to visualize the corresponding gameplay. 
> * Double click to unselect.

<p align="center">
<div id="selector-view"></div>
<iframe id="episode-view" src="assets/data/episode_1_0_00.html" scrolling=no height='840' width='600' frameborder='0'></iframe>
<script type="text/javascript">
    var spec = getSpec();
    var view = new vega.View(vega.parse(spec), {
      renderer:  'canvas',
      container: '#selector-view',
      hover:     true
    }).run();

    const episode_view = document.getElementById("episode-view");
    view.addEventListener('click', function(event, item) {
      if (item != null) {
        console.log('clicked', item.datum.home_id, item.datum.away_id);
        episode_view.src = "assets/data/episode_" + item.datum.home_id + "_" + item.datum.away_id + "_00.html";
      }
    });
</script>
</p>

[^1]: Lanctot, Marc, Vinicius Zambaldi, Audrunas Gruslys, Angeliki Lazaridou, Karl Tuyls, Julien Pérolat, David Silver, and Thore Graepel. "A unified game-theoretic approach to multiagent reinforcement learning." (2017).