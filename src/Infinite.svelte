<style>
  .infinite{
    width: var(--size);
    height: var(--size);
    border-radius: 2px;
    background: blue;
    margin: 1em;
    flex: none;
  }
</style>

<script>  
  import {onMount} from "svelte";
  export let transition;
  export let opts = {};
  export let style = "";
  let visible = false;
  const duration = (opts.duration || 400);
  onMount(() => { 
    setTimeout(function fn(){
      visible = !visible
      setTimeout(fn, duration)
    }, duration);
  })
</script>

{#if visible}
  <div class="infinite" {style} transition:transition|local={opts}>
    <slot/>
  </div>
{/if} 