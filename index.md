---
layout: default
title: "NeuPL: Neural Population Learning"
---

# Interactive Visualization

Visualization of 8 distinct `running-with-scissors` strategies executed by the same `NeuPL` agent.

> Click on a cell in the payoff matrix to visualize the corresponding gameplay. Double click to unselect.

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

## Header 2

> This is a blockquote following a header.
>
> When something is important enough, you do it even if the odds are not in your favor.

### Header 3

```js
// Javascript code with syntax highlighting.
var fun = function lang(l) {
  dateformat.i18n = require('./lang/' + l)
  return true;
}
```

```ruby
# Ruby code with syntax highlighting
GitHubPages::Dependencies.gems.each do |gem, version|
  s.add_dependency(gem, "= #{version}")
end
```

#### Header 4

*   This is an unordered list following a header.
*   This is an unordered list following a header.
*   This is an unordered list following a header.

##### Header 5

1.  This is an ordered list following a header.
2.  This is an ordered list following a header.
3.  This is an ordered list following a header.

###### Header 6

| head1        | head two          | three |
|:-------------|:------------------|:------|
| ok           | good swedish fish | nice  |
| out of stock | good and plenty   | nice  |
| ok           | good `oreos`      | hmm   |
| ok           | good `zoute` drop | yumm  |

### There's a horizontal rule below this.

* * *

### Here is an unordered list:

*   Item foo
*   Item bar
*   Item baz
*   Item zip

### And an ordered list:

1.  Item one
1.  Item two
1.  Item three
1.  Item four

### And a nested list:

- level 1 item
  - level 2 item
  - level 2 item
    - level 3 item
    - level 3 item
- level 1 item
  - level 2 item
  - level 2 item
  - level 2 item
- level 1 item
  - level 2 item
  - level 2 item
- level 1 item

### Small image

![Octocat](https://github.githubassets.com/images/icons/emoji/octocat.png)

### Large image

![Branching](https://guides.github.com/activities/hello-world/branching.png)


### Definition lists can be used with HTML syntax.

<dl>
<dt>Name</dt>
<dd>Godzilla</dd>
<dt>Born</dt>
<dd>1952</dd>
<dt>Birthplace</dt>
<dd>Japan</dd>
<dt>Color</dt>
<dd>Green</dd>
</dl>

```
Long, single-line code blocks should not wrap. They should horizontally scroll if they are too long. This line should be long enough to demonstrate this.
```

```
The final element.
```
