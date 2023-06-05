# postcss-px-to-viewport-pc
[![NPM version](https://badge.fury.io/js/postcss-px-to-viewport-pc.svg)](http://badge.fury.io/js/postcss-px-to-viewport-pc)

English | [中文](README_CN.md) 

A plugin for [PostCSS](https://github.com/postcss/postcss) that generates viewport units (vw, vh, vmin, vmax) from pixel units.

## Demo

If your style needs to adjust the width based on the viewport size, this script can convert the px unit in your CSS to vw, where 1vw is equal to 1/100 of the viewport width.

Add an adaptive PC terminal to set a fixed size, no longer based on the PC window, but based on self setting labels for adaptation

The configuration is the same as that of postcss px to viewport, which needs to be used in conjunction with selectorBlackList to set non verified class names

//Specify classes that are not converted to window units, which can be customized and can be added infinitely. It is recommended to define one or two universal class names

### Input

```css
.class {
  margin: -10px .5vh;
  padding: 5vmin 9.5px 1px;
  border: 3px solid black;
  border-bottom-width: 1px;
  font-size: 14px;
  line-height: 20px;
}

.class2 {
  padding-top: 10px; /* px-to-viewport-ignore */
  /* px-to-viewport-ignore-next */
  padding-bottom: 10px;
  /* Any other comment */
  border: 1px solid black;
  margin-bottom: 1px;
  font-size: 20px;
  line-height: 30px;
}

@media (min-width: 750px) {
  .class3 {
    font-size: 16px;
    line-height: 22px;
  }
}
```

### Output
```css
.class {
  margin: -3.125vw .5vh;
  padding: 5vmin 2.96875vw 1px;
  border: 0.9375vw solid black;
  border-bottom-width: 1px;
  font-size: 4.375vw;
  line-height: 6.25vw;
}

.class2 {
  padding-top: 10px;
  padding-bottom: 10px;
  /* Any other comment */
  border: 1px solid black;
  margin-bottom: 1px;
  font-size: 6.25vw;
  line-height: 9.375vw;
}

@media (min-width: 750px) {
  .class3 {
    font-size: 16px;
    line-height: 22px;
  }
}
```

## Getting Started

### Installation
Add via npm
```
$ npm install postcss-px-to-viewport-pc --save-dev
```
or yarn
```
$ yarn add -D postcss-px-to-viewport-pc
```