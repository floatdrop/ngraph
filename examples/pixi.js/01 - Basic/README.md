This is a really basic setup to render graph with PIXI.js

This examples uses:

* [ngraph.forcelayout](https://github.com/anvaka/ngraph.forcelayout) - For this example we will require layout algorithm;
* [ngraph.generators](https://github.com/anvaka/ngraph.generators) -  Graph generators, to create a predefined graph;
* [ngraph.physics.simulator](https://github.com/anvaka/ngraph.physics.simulator) - To adjust force directed layout arguments

All these modules are exported inside `index.js` file:

``` js
module.exports.layout = require('ngraph.forcelayout');
module.exports.createGraph = require('ngraph.generators');
module.exports.physics = require('ngraph.physics.simulator');
```

And are built into browser-compatible script with:

```
browserify -s ngraph index.js > bundle.js
```

Now any page which includes `bundle.js` file has access to modules via `ngraph`
namespace:

```
// You'll find this code inside index.html:
// It creates a grid-graph, with 40 columns and 40 rows
var graph = ngraph.createGraph.grid(40, 40);
```