---
layout: default
title: 'NeuPL: Neural Population Learning'
---

# Interactive Visualization

Visualization of 8 distinct `running-with-scissors` strategies executed by the same `NeuPL` agent.

> * Click on a cell in the payoff matrix to visualize the corresponding gameplay. 
> * Double click to unselect.

<div id="demo" align='center'>
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
</div>
