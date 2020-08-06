# Vue Scroll To Top 

[![npm](https://img.shields.io/npm/v/vue-backtotop.svg)](https://www.npmjs.com/package/vue-simple-scroll-up)
![npm bundle size](https://img.shields.io/bundlephobia/min/vue-simple-scroll-up)

Simple and lightweight back to top Vue.js component which scrolls up smoothly when clicked. 

## Demo

See [demo](https://anasaraid.me/vue-simple-scroll-up-example/).

## Install via npm

```bash
npm i vue-simple-scroll-up --save
```
## Import and use

Import for global usage
```javascript
import Vue from 'vue'
import scrollUp from 'vue-simple-scroll-up'

Vue.use(scrollUp)
...
```

Or on a single component
```javascript
import scrollUp from 'vue-simple-scroll-up'
...
},
components: { 
    'vue-scroll-to-top': scrollUp
}
...
```

## Props

| Property  |  Type |  Default Value |  Description |
| ------------ | ------------ | ------------ | ------------ |
|text  |  String  |  'Back to top'  | Button description.|
|visibleY  |  Number  |  300  | Show button when scrollY equals to visibleY value.|
| duration  |  Number  |  250    | Scrolling animation duration.|

## Events

| Name                   | Description                                                              |
|------------------------|--------------------------------------------------------------------------|
| scrolledOnTop               | Triggered when scrolling finished (can be used to refresh content)  |

## How to use

Add this into your files:
```html
<vue-scroll-to-top text="Back to top" :visibleY="1200" :duration="1000"></vue-scroll-to-top>
```

Overwrite this css properties to change button style:
```css
.vue-scroll-button{
  background-color: #4CAF50; /* button background color */
  color:white; /* button text color */
}
.vue-scroll-button:hover{
  box-shadow: 0 12px 14px -6px #4CAF50; /* button shadow */
}
```