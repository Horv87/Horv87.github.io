---
layout: post
title:  "Never look for small imprints again"
date:   2016-12-03 11:21:00 +0100
categories: javascript
---
Recently i decided to learn about [**WebExtensions**](https://developer.mozilla.org/en-US/Add-ons/WebExtensions) an API to develop Browser Extensions for firefox and chrome.
In my opinion the best way to learn a new technology is by solving a real world problem. One real world problem i had was often having 
to look for really small imprint links on websites. 

The [documentation](https://developer.mozilla.org/en-US/Add-ons/WebExtensions) for WebExtensions is really well written, so it was quite easy to get going.
My ImprintFinder Extensions works with just a little bit of `regex` black magic:
{% highlight javascript %}
var x = document.links;
var len = x.length;
for (var i = 0; i < len; i++){
var regEx = /Impressum|Imprint/g;

	if (regEx.test(x[i].text)){
		x[i].click();
	}
}
{% endhighlight %}

The full project is on github so [**check it out**](https://github.com/Horv87/ImprintFinder) or even better try to make your own little WebExtension.
