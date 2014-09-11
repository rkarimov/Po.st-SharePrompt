SharePrompt Feature
============

SharePrompt is another sharing feature from Po.st that surfaces a floating sharing tool from either the bottom, sides or center of your page. At a certain point while the user is naturally scrolling down the page, SharePrompt will appear encouraging your users to share the content they are currently reading and engaged with.

You can choose to have this floating sharing tool appear after a user scrolls down 25%, 50% or 75% of the page they are currently reading. (Please review the "show" parameter under Options).

To install the SharePrompt feature you will need to copy, host, and reference a couple of files on your site, as well as include the example code or configured code directly on your site.

This feature can be used by itself or as an additional feature with your existing Po.st Sharing Tool integration.


Installation
------------

1. Add r1sp.css to <HEAD> section `<link rel="stylesheet" href="r1sp.css" />`.
2. Add share-promt.min.js before </body> `<script src="share-promt.min.js"></script>`.
3. Add component's script with options

```
<script>
window.sharePromtConfig = {
  widgetPublisherKey: 'pubkey',
  type: 'toolbar',
  position: 'bottom-right',
  effect: 'slide',
  show: 'scroll.end',
  post_widget: {
    buttons: ['facebook', 'twitter', 'mail', 'post'],
    size: 'large'
  },
  template: '<a class="r1sp__close"data-action="close"></a><div class="r1sp__share-title">Share with friends:</div>{{widget}}'
};
</script>
```

4 SharePrompt Examples to Choose From
-------------------------------------

There are several versions of this feature available, so we’re confident you’ll find the one that best fits your site! If you're looking for something a little more custom, the integration instructions below will allow you to do that. Reach out to publishers@po.st if you have any questions.

#### 1. SharePrompt:Lightbox example

Click here to view this example: http://po.st/SharePromptLightbox

The **SharePrompt:Lightbox** will appear in an overlay message in the center of your screen while it dims your article page content.

```
<script>
 window.sharePromtConfig = {
   widgetPublisherKey: 'test',
   type: 'lightbox',
   overlay: true,
   effect: 'fade',
   show: 1000,
   post_widget: {
     buttons: ['facebook', 'twitter', 'mail', 'post'],
     size: 'large'
   },
   template: '<a class="r1sp__close" data-action="close"></a><div class="r1sp__share-title">Share with friends:</div>{{widget}}'
 };
</script>
```

#### 2. SharePrompt:Toolbar-Bottom example

Click here to view this example: http://po.st/SharePromptToolbarBottom

The **SharePrompt:ToolbarBottom** will appear at the very bottom of your page once your viewers have scrolled down a certain distance.

```
<script>
  window.sharePromtConfig = {
    widgetPublisherKey: 'demo',
    type: 'toolbar',
    position: 'bottom',
    overlay: true,
    offset_position: {
      bottom:0
    },
    effect: 'slide',
    offset_show: 500,
    show: {afterElement: document.getElementById('sharePromptId')},
    post_widget: {
      buttons: [{id:'facebook', look:'native'}, {id:'twitter', look:'native'}, {id:'mail', look:'native'}, {id:'post-share', look:'native'}],
      size: 'small'
    },
    template: '<a class="r1sp__close" data-action="close"></a><div class="r1sp__share-inl r1sp__share-inl--small">Share with friends:</div> <div class="r1sp__widget-inlineb">{{widget}}</div>'
  };
</script>
```

#### 3. SharePrompt:Toolbar-Bottom-Right example

Click here to view this example: http://po.st/SharePromptToolbarBottomRight

The **SharePrompt:ToolbarBottomRight** will appear at the bottom-right of your page once your viewers have scrolled down a certain distance.

```
<script>
  window.sharePromtConfig = {
    widgetPublisherKey: 'demo',
    type: 'toolbar',
    position: 'bottom-right',
    overlay: true,
    offset_position: {
      bottom:0
    },
    effect: 'slide',
    offset_show: -1000,
    show: 'scroll.end',
    post_widget: {
      buttons: [{id:'facebook', look:'native'}, {id:'twitter', look:'native'}, {id:'mail', look:'native'}, {id:'post-share', look:'native'}],
      size: 'small'
    },
    template: '<a class="r1sp__close" data-action="close"></a><div class="r1sp__share-inl">Share with friends:</div> <div class="r1sp__widget-inlineb">{{widget}}</div>'
  };
</script>
```

#### 4. SharePrompt:Toolbar-Bottom-Right example

Click here to view this example: http://po.st/SharePromptToolbarBottomLeft

The **SharePrompt:ToolbarBottomLeft** will appear at the bottom-left of your page once your viewers have scrolled down a certain distance.

```
<script>
  window.sharePromtConfig = {
    widgetPublisherKey: 'demo',
    type: 'toolbar',
    position: 'bottom-left',
    effect: 'slide',
    offset_show: -1000,
    show: 'scroll.end',
    post_widget: {
      buttons: [{id:'facebook', look:'native'}, {id:'twitter', look:'native'}, {id:'mail', look:'native'}, {id:'post-share', look:'native'}],
      size: 'xlarge'
    },
    template: '<a class="r1sp__close" data-action="close"></a><div class="r1sp__share-inl">Share with friends:</div> <div class="r1sp__widget-inlineb">{{widget}}</div>'
  };
</script>
```

Options
-------

<table class="table">
<thead>
<tr><th>Name</th><th>Value</th><th>Description</th></tr>
</thead>
<tbody>
<tr>
<td>widgetPublisherKey</td>
<td>&nbsp;</td>
<td>Publisherkey to&nbsp;initialize the widget.&nbsp;<strong>Not required, if Po.st widget is already included.</strong></td>
</tr>
<tr>
<td>type</td>
<td>toolbar/lightbox</td>
<td>
<p>Component type:</p>
<p>lightbox</p>
<p>toolbar</p>
</td>
</tr>
<tr>
<td>position</td>
<td>
<p>bottom/bottom-right/bottom-left/top/top-left/top-right</p>
</td>
<td><strong>Only for toolbar.&nbsp;</strong>Allows you to set the position of toolbar</td>
</tr>
<tr>
<td>overlay</td>
<td>true/<strong>false</strong></td>
<td><strong>Only for lightbox</strong></td>
</tr>
<tr>
<td>effect</td>
<td>fade/slide/<strong>none</strong></td>
<td>CSS3 animation</td>
</tr>
<tr>
<td>show</td>
<td>scroll.start/scroll.end/page.ready/{ afterElement: [element] }/[number]</td>
<td>
<p><strong>scroll.start -&nbsp;</strong>When starts scrolling</p>
<p><strong>scroll.end -&nbsp;</strong>Show component when we come to end of the page</p>
<p><strong>page.ready -&nbsp;</strong>When the page is loaded</p>
<p><strong>{afterElement: element} -&nbsp;</strong>Element after which the component is called<em>(Example show: {afterElement: document.getElementById('show-lightbox')})</em></p>
<p><strong>number -&nbsp;</strong>Can be px or&nbsp;%<strong>.&nbsp;</strong></p>
<p><em>show: 1000; show: '20%'</em></p>
</td>
</tr>
<tr>
<td>offset_show</td>
<td>number (Support percent) / function</td>
<td>Example offset_show:-100. Show component before 100px, when we scroll to the end of the page</td>
</tr>
<tr>
<td>offset_position</td>
<td>
<p>{</p>
<p>top/left/bottom/right</p>
<p>}</p>
</td>
<td>
<p>Offset for component position.</p>
<p><strong>Default:&nbsp;</strong>20px.</p>
</td>
</tr>
<tr>
<td>skin</td>
<td>&nbsp;</td>
<td>
<p>Set custom view for component</p>
<p>Default value: default (r1sp--default).</p>
<p>Example: skin: 'gennewlayout' = &lt;div class="r1sp--gennewlayout"&gt;&lt;/div&gt;</p>
</td>
</tr>
<tr>
<td>post_widget</td>
<td>&nbsp;</td>
<td>Widget JS API. Read more&nbsp;<a href="/hc/en-us/articles/200435553-Javascript-API" target="_blank" rel="nofollow">http://support.po.st/hc/en-us/articles/200435553-Javascript-API</a></td>
</tr>
<tr>
<td>template</td>
<td>&nbsp;</td>
<td>
<p>Template for component. Placeholder {{widget}} init post_widget</p>
<p><strong>Default:</strong>'&lt;a class="r1sp__close" data-action="close"&gt;&lt;/a&gt;&lt;div class="r1sp__share-inl"&gt;Share with friends:&lt;/div&gt; {{widget}}'</p>
</td>
</tr>
</tbody>
</table>

Button close
---

You can use your own element and styles. You just need set the attribute data-action="close"

Example:

    <a class="r1sp__close" data-action="close">

or

    <a class="yourownclass" data-action="close">

After init
--

After the script load event fires, the code on the page will look like this example

``` js
<div class="r1sp--toolbar r1sp--position_bottom-right r1sp--default r1sp--slide-right">
    <div class="r1sp__content"> [Option template] </div>
</div>
```

Container classes
---

The names of classes that appear in the re-generated code from the above after init example

<table class="table">
<thead>
<tr><th>Name</th><th>Description</th><th>Example</th></tr>
</thead>
<tbody>
<tr>
<td>r1sp--[type]</td>
<td>Option type</td>
<td>r1sp--toolbar/r1sp--lightbox</td>
</tr>
<tr>
<td>r1sp--position-[position]</td>
<td>Optionposition</td>
<td>r1sp--position-bottom_right/r1sp--position-bottom</td>
</tr>
<tr>
<td>r1sp--[skin]</td>
<td>Optionskin</td>
<td>r1sp--default/r1sp--yourownskin</td>
</tr>
<tr>
<td>r1sp--[effect]</td>
<td>Optioneffect</td>
<td>
<p>r1sp–fade (For fade)</p>
<p>r1sp--slide-bottom (For effect:slide and position:bottom)</p>
<p>r1sp--slide-bottom-left (For effect:slide and position:bottom-left)</p>
<p>r1sp--slide-bottom-right (For effect:slide and position:bottom-right)</p>
<p>r1sp--slide-top (For effect:slide and position:top)</p>
<p>r1sp--slide-top-left (For effect:slide and position:top-left)</p>
<p>r1sp--slide-top-right (For effect:slide and position:top-right)</p>
</td>
</tr>
</tbody>
</table>

API
--

You can use JS API functions to call for components.

<table class="table">
<thead>
<tr><th>Method</th><th>Description</th></tr>
</thead>
<tbody>
<tr>
<td>sharePromptJsApi.activate(options)</td>
<td>Init component with options.</td>
</tr>
<tr>
<td>sharePromptJsApi.deactivate()</td>
<td>Remove component from DOM</td>
</tr>
<tr>
<td>sharePromptJsApi.show()</td>
<td>Show component</td>
</tr>
<tr>
<td>sharePromptJsApi.hide()</td>
<td>Hide component</td>
</tr>
</tbody>
</table>
