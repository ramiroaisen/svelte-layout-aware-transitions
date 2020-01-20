# Svelte Layout Aware Transitions [DEMO](https://ramiroaisen.github.io/svelte-layout-aware-transitions/)

### Install
```sh
npm i svelte-layout-aware-transitions
```


### Use
```html
<script>
	import {
    	slideLeft,
      flyLeft,
      
      slideRight,
      flyRight,
      
      slideDown,
      flyDown,
      
      slideUp,
      flyUp
    } from "svelte-layout-aware-transitions";
</script>

<div transition:slideLeft={opts}></div>
```

### Why?
Transform based transitions are great, they're GPU accelerated and all. But sometimes you need to incorporate an element to a layout with a transition that affects also the other elements in the layout.
Sometimes you can achieve this using animate but sometimes not (I think)

### Notes
These transitions make use of negative margins, and sets the display to relative and the z-index to -1 during the transition

Fly transitions are equal to slide but adding the fade effect.

All transitions accepts the same params with the same defaults:
```js
  duration: 400
  delay: 0
  easing: cubicOut // (see svelte/easing)
```

### TODO
Add more transitions

Change the name to a better (shorter) one