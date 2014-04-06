---
layout: post
title: d3 data transitions in AngularJS
---

Just whipped up a demonstration of implementing data transitions via d3 through AngularJS directives.

<iframe class="example-frame"
        src="http://bl.ocks.org/chrisirhc/raw/10003441/"
        height="250" width="510"><!-- Workaround this tag getting munged --></iframe>

See it in action on [on Plunker](http://plnkr.co/edit/8h9pvOk3pdIAlFc22uDA?p=preview).

The directive is actually very simple:

{% highlight js %}
angular.module('plunker', [])
.directive('transAttr', function () {
  return {
    link: function (scope, element, attr) {
      var d3sel = d3.select(element[0]);

      // Watch for changes in the object's values
      scope.$watchCollection(attr.transAttr, function (newAttrs) {
        // Format attribute object into entry format
        newAttrs = d3.entries(newAttrs);

        // Create a new transition
        var trans = d3sel.transition().duration(1000);

        // Apply each attribute as a transition
        newAttrs.forEach(function (attr) {
          trans.attr(attr.key, attr.value);
        });
      });
    }
  }
})
{% endhighlight %}

