<style>
  .infinite{
    width: var(--size);
    height: var(--size);
    border-radius: 50%;
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
    const timeout = duration + 500;
    const fn = () => {
      visible = !visible;
      setTimeout(fn, duration);
    }

    setTimeout(fn, 10);
  })
</script>

{#if visible}
  <div class="infinite" {style} transition:transition|local={opts}>
    <slot/>
  </div>
{/if} 