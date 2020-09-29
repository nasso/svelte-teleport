# svelte-teleport

A Svelte component to teleport elements across the DOM.

## Example usage

You can also [try it out on the REPL](https://svelte.dev/repl/76df852a8ae748ed95b91ed1cf683a3c?version=3.28.0).

```svelte
<script>
  import { Portal } from 'svelte-teleport';

  let portal_a;
  let portal_b;
</script>

<h1>Example</h1>

<button on:click={() => portal_a.teleport_to(portal_b)}>Teleport!</button>

<h2>Portal A</h2>

<Portal bind:this={portal_a}>
  <textarea>Hello world!</textarea>
</Portal>

<h2>Portal B</h2>

<Portal bind:this={portal_b}></Portal>
```
