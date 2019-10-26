# Simple-tabs
Very simple tabs created with jQuery and CSS

This is very simple script:

HTML:

```html
<div class="tabs-menu">
	<div id="tab-1" class="tabs-menu-item active">Tab 1</div>
	<div id="tab-2" class="tabs-menu-item">Tab 2</div>
	<div id="tab-3" class="tabs-menu-item">Tab 3</div>
</div>

<div class="tabs">
	<div class="tab tab-1 current">
		Lorem ipsum dolor sit amet, consectetur adipiscing elit. Sed sit amet nisi nec ex pretium tincidunt. Phasellus luctus sodales luctus. Suspendisse fermentum magna eu sagittis tincidunt. Phasellus vulputate sollicitudin feugiat. Vivamus enim nunc, sagittis at elit id, feugiat auctor est. Curabitur lacinia sit amet diam non vehicula. Pellentesque eget felis vel lacus blandit ornare sed et felis. Integer gravida nec tellus vitae feugiat. Vivamus non elit velit. Proin quis justo sem. Aenean commodo orci purus, quis commodo mauris lobortis sit amet. Morbi ac vestibulum dolor. In imperdiet leo ac nisl vestibulum mollis.
	</div>
	<div class="tab tab-2">
		Curabitur arcu arcu, efficitur nec suscipit sit amet, consequat non sapien. Vestibulum ante ipsum primis in faucibus orci luctus et ultrices posuere cubilia Curae; Fusce rutrum accumsan nunc, non sollicitudin justo tincidunt in. Mauris tortor lectus, convallis nec tortor a, egestas consequat eros. Curabitur molestie cursus blandit. Pellentesque tincidunt tortor mauris, ut imperdiet purus ornare nec. Donec pharetra nunc in ligula accumsan finibus. Nullam hendrerit volutpat ligula, a varius massa fermentum non. Nulla quis nibh aliquet, sagittis lectus tempus, rhoncus lectus. Quisque sagittis facilisis augue ut consectetur. Suspendisse potenti. Pellentesque auctor nisl sollicitudin ultricies venenatis.
	</div>
	<div class="tab tab-3">
		Nam id massa at urna dignissim lacinia eget in massa. Proin id fringilla diam. Etiam tristique, leo fermentum ornare ultricies, urna velit feugiat lacus, sit amet tincidunt ligula erat nec turpis. Aenean vehicula congue turpis at sagittis. Etiam non vestibulum enim. Mauris congue ante sit amet neque semper, id pharetra arcu vehicula. Vestibulum felis nunc, sodales non massa ut, sodales condimentum quam. Vivamus vehicula tellus vitae justo consectetur, at aliquam augue congue. Curabitur tristique felis eu cursus suscipit. Suspendisse potenti. Aliquam risus quam, pharetra a fermentum id, faucibus eu augue. Donec vehicula fringilla ligula sit amet tempus. Sed molestie, nunc nec vulputate consequat, ante massa efficitur elit, in pellentesque erat magna vitae erat. Duis fermentum cursus dolor, sed mattis mi.
	</div>
</div>
```

Most important here are classes cause we will be refering to them later in jQuery.

CSS:

```css
/* hiding and showing tabs */

.tabs div {
	display:none;
}

.tabs div.current {
	display:block;
}

/* highlighting selected tab menu */

.tabs-menu div.active {
	background:#000000; color:#ffffff;
}
```

The fun part of it is that you can create different styles for .tabs div and .tabs div.current (adding transitions, opacity and so on so tabs will change with animations.

jQuery:

```javascript
tabSelector = $('.tabs-menu div');
tab = $('.tab');
	
tabSelector.bind('click', function() {
	tabSelector.removeClass('active');
	$(this).addClass('active');
	tabId = $(this).attr('id');
	tab.removeClass('current');
	tab = $('.' + tabId).addClass('current');
	tab.addClass('current');
});
```

And that's it :) We just reffering to elements and changing they're classes all the magic happens in CSS :)
