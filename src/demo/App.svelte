<script>
  import { onMount } from 'svelte';
  import Component from './Component.svelte';
  import Portal from './Portal.svelte';

  let current_portal;

  let portal_a;
  let portal_b;
  let portal_c;

  onMount(() => {
    current_portal = portal_a;
  });

  function onSent(e) {
    current_portal = e.detail;
  }
</script>

<div class="teleporter">
  <Portal bind:this={portal_a} on:sent={onSent} >
    <Component />
    <textarea style="resize: vertical;"></textarea>
  </Portal>
  <button on:click={() => current_portal.teleport_to(portal_a)} >Teleport!</button>
</div>

<div class="teleporter">
  <Portal bind:this={portal_b} on:sent={onSent} />
  <button on:click={() => current_portal.teleport_to(portal_b)} >Teleport!</button>
</div>

<div class="teleporter">
  <Portal bind:this={portal_c} on:sent={onSent} />
  <button on:click={() => current_portal.teleport_to(portal_c)} >Teleport!</button>
</div>

<style>
  .teleporter {
    display: inline-flex;

    background: #EFEFEF;
    padding: 8px;
    border-radius: 16px;

    width: 200px;

    flex-direction: column;
  }

  button {
    margin: 0px;
    border-radius: 8px;
  }
</style>
