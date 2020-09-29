<script>
  import { createEventDispatcher } from 'svelte';

  const dispatch = createEventDispatcher();

  let contents;

  export function take_contents(src_contents, src) {
    if (src_contents === contents) { return; }

    while (src_contents.firstChild) {
      contents.appendChild(src_contents.firstChild);
    }

    dispatch('received', src);
  }

  export function teleport_to(target) {
    target.take_contents(contents, this);

    dispatch('sent', target);
    return target;
  }
</script>

<div bind:this={contents}>
  <slot />
</div>

<style>
  div {
    display: contents;
  }
</style>
