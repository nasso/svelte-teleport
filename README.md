# svelte-teleport

A Svelte component to teleport elements across the DOM.

## Example usage

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
