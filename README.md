# hexo-tag-demo

Use {% demo %} tag to create a demo area (html, css, javascript) in the post content.

## Installation

```bash
npm install hexo-tag-demo --save
```

## Usage

Syntax:

```
{% demo [title] %}
  <intro></intro>
  <template></template>
  <script></script>
  <style></style>
{% enddemo %}
```

Live Example: [example.md](https://raw.githubusercontent.com/laomao800/hexo-tag-demo/master/example.md)

```html
{% demo hexo-tag-demo %}
<intro>
An example for hexo-tag-demo.

The `<intro>` tag supports __markdown__.
</intro>

<template>
  <div id="colorbox"></div>
  <button id="demo-button">Click Me</button>
</template>

<script>
  document.getElementById('demo-button').onclick = function() {
    var randomColor = '#' + Math.random().toString().substr(2,6);
    document.getElementById('colorbox').innerHTML = randomColor;
    document.getElementById('colorbox').style.background = randomColor;
  }
</script>

<style>
  #colorbox {
    border: 1px solid #ddd;
    height: 150px;
    width: 200px;
    line-height: 150px;
    text-align: center;
    margin-bottom: 20px;
    color: #fff;
  }
  #demo-button {
    padding: 5px 10px;
  }
</style>
{% enddemo %}
```

Output Screenshot:

![Example Output Screenshot](https://raw.githubusercontent.com/laomao800/hexo-tag-demo/master/screenshot.png)

## New in 0.2.0

`<template>`, `<script>`, `<style>` tag support `for-show` and `for-run` attribute.

In some special cases, if you need to show some code different from the running demo code, you can use this two attributes.

Set the `for-run` will just running in the demo area but not showing in the expansion. Set the `for-show` attribute will show the code just in the expansion but not running it.

Example:

```html
{% demo %}
<template for-run>
  <button onclick="alert('something')">alert</button>
</template>

<template for-show>
  <button>know nothing</button>
</template>
{% enddemo %}
```
