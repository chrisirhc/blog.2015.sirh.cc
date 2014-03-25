---
layout: post
title: Data visualization transitions in AngularJS
---

Just whipped up a demonstration of implementing data transitions via d3 through AngularJS directives.

See it in action on [on Plunker](http://plnkr.co/edit/8h9pvOk3pdIAlFc22uDA?p=preview).

The directive is actually very simple:

{% highlight js %}
angular.module('plunker', [])
.directive('transAttr', function () {
  return {
    link: function (scope, element, attr) {
      var d3sel = d3.select(element[0]);
      scope.$watchCollection(attr.transAttr, function (newAttrs) {
        newAttrs = d3.entries(newAttrs);
        var trans = d3sel.transition().duration(1000);
        newAttrs.forEach(function (attr) {
          trans.attr(attr.key, attr.value);
        });
      });
    }
  }
})
{% endhighlight %}

Unfortunately, AngularJS animations doesn't give enough power to perform such animations. `move` re-arranges DOM element order.
