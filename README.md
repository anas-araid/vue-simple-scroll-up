<div align="center">
  <h1>Simple Scroll To Top</h1>
  <img src="https://img.shields.io/npm/v/vue-simple-scroll-up" alt="version" align="center" />
  <img src="https://img.shields.io/npm/dt/vue-simple-scroll-up" alt="npm" align="center">
  <img src="https://img.shields.io/bundlephobia/min/vue-simple-scroll-up" alt="npm bundle size" align="center" /> 
  <img src="https://img.shields.io/github/license/asdf1899/vue-simple-scroll-up" alt="license" align="center" />
  <br>
  <img src="https://anasaraid.me/hosting/vue-simple-scroll-up/logo.png" alt="logo" align="center" width="320px" />
  <p>Simple and lightweight 'back to top' Vue.js component which scrolls up smoothly when clicked.</p>
</div>
<br><br>
<br><br>

Can be used also to refresh data to load newest contents using *scrolledOnTop* event.

> Inspired by Instagram, Linkedin, Reddit etc. scroll to refresh button. [[Images]](https://github.com/asdf1899/vue-simple-scroll-up#inspired-by-instagram-linkedin-reddit-etc-scroll-to-refresh-buttons)

<br>

## Demo
<div align="center">
  <img src="https://anasaraid.me/hosting/vue-simple-scroll-up/example.gif" width="320px"/>
</div>

See [demo](https://anasaraid.me/vue-simple-scroll-up-example/).


# Getting Started

## Install via npm

```bash
npm i vue-simple-scroll-up --save
```

## Import

Import for global usage

```javascript
import Vue  from 'vue'
import scrollUp  from 'vue-simple-scroll-up'

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
## Usage

Add this into your files:

```html
<vue-scroll-to-top text="Back to top" :visibleY="1200" :duration="1000"></vue-scroll-to-top>
```

To trigger *scrolledOnTop* event:

```html
<vue-scroll-to-top text="Back to top" @scrolledOnTop="yourReloadFunction()"></vue-scroll-to-top>
```

Overwrite this css properties to change button style:

```css
.vue-scroll-button{
  background-color: #4CAF50; /* button background color */
  color: white; /* button text color */
}
.vue-scroll-button:hover{
  box-shadow: 0 12px 14px -6px #4CAF50; /* button shadow */
}
```

## Props

| Property | Type | Default Value | Description |
| ------------ | ------------ | ------------ | ------------ |
| text | String | 'Back to top' | Button description.|
| visibleY | Number | 400 | Show button when scrollY equals to visibleY value.|
| duration | Number | 800 | Scrolling animation duration.|

## Events

| Name | Description |
|------------------------|--------------------------------------------------------------------------|
| scrolledOnTop | Triggered when scrolling finished (can be used to refresh content) |


## Contributing

Finding bugs, sending pull requests or improving the docs - any contribution is welcome and highly appreciated.

<br>

### Inspired by Instagram, Linkedin, Reddit etc. scroll to refresh buttons


<img  src="https://anasaraid.me/hosting/vue-simple-scroll-up/insta.jpg"  width="320px"/><br>
<img  src="https://anasaraid.me/hosting/vue-simple-scroll-up/reddit.jpg"  width="320px"/>

## License
[MIT](https://github.com/asdf1899/vue-simple-scroll-up/blob/master/LICENSE.md)
