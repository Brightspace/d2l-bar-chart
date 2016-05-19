#d2l-bar-chart

[![Bower version][bower-image]][bower-url]
[![Build status][ci-image]][ci-url]
[![Dependency Status][dependencies-image]][dependencies-url]

A simple bar chart using d3 that provides the option of displaying an axis and/or showing a tooltip on hover.

## Installation

`d2l-bar-chart` can be installed from [Bower][bower-url]:
```shell
bower install d2l-bar-chart
```

## Usage

Include [webcomponent.js](http://webcomponents.org/polyfills/) "lite" polyfill (for browsers who don't natively support web components), then import `bar-chart.html`:

```html
<head>
	<script src="https://s.brightspace.com/lib/webcomponentsjs/0.7.21/webcomponents-lite.min.js"></script>
	<link rel="import" href="../d2l-bar-chart/bar-chart.html">
</head>

<body>
	   <d2l-bar-chart options='{..}' width='..' height='..' data='[..]'></d2l-bar-chart>
</body>
```

### Attributes

**options** - Object to set different settings for the bar chart
```
{
	showAxis: {Boolean} : Default = false
	showTooltip: {Boolean} : Default = false
	barSpaces: {Number} : Padding between bar rectangles. Default is 3
	axisHeight: {Number} : Height of axis text. Default is 10
	axisType: {string} : text or numeric
}
```
**width** - Width of the bar chart

**height** - Height of the bar chart

**data** - List of objects that contain the data for the bar chart
```
[
	{
		value: {Number}
		fill: {String} - Bar rect fill color. Html color code. If not provided will default to #9B9B9B
		hoverFill: {String} - On hover bar rect fill color. Html color code. If not provided will not apply
		info: {
			start: {Number} - Start of score range
			end: {Number} - End of score range. Refer to note below about tooltip display
			label: {String} Used on the axis and tooltip if axisType is text
			max: {Number} Maximum number the bar represents
		}
	}
]
```

**NOTE** : Tooltip displays the grade range in the following format: `{info.start}% - {info.end - 1}%`.
**NOTE** : `Up to info.max points` (When displayed as text)

## Usage in Production

In production, it's recommended to use a build tool like [Vulcanize](https://github.com/Polymer/vulcanize) to combine all your web components into a single import file. [More from the Polymer Docs: Optimize for Production](https://www.polymer-project.org/1.0/tools/optimize-for-production.html)...

It is not recommend to inline d3 when importing the component but rather to externally include it from a CDN. Vulcanize can be used in the following manner to achieve this:

```
vulcanize --strip-exclude d3-import.html
```
## Contributing

Feel free to contribute. Please submit a **PR**. Committing directly against this repository is **highly discouraged**.

## Code Style
See [EditorConfig](http://editorconfig.org) for information about the rules used in this repo.

[bower-url]: http://bower.io/search/?q=d2l-bar-chart
[bower-image]: https://img.shields.io/bower/v/d2l-bar-chart.svg
[ci-url]: https://travis-ci.org/Brightspace/d2l-bar-chart
[ci-image]: https://travis-ci.org/Brightspace/d2l-bar-chart.svg?branch=master
[dependencies-url]: https://david-dm.org/brightspace/d2l-bar-chart
[dependencies-image]: https://img.shields.io/david/Brightspace/d2l-bar-chart.svg