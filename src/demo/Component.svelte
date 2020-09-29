<script context="module">
  let render_count = 0;
</script>

<script>
  render_count++;

  let counter = 0;
</script>

<div>
  Rendered {render_count} { render_count === 1 ? 'time' : 'times' }.
  <p>
    Clicked: {counter}
  </p>
  <button on:click={() => counter++}>Increment</button>
</div>

<style>
  div {
    border: 1px solid rgba(0, 0, 0, 0.2);
    margin-bottom: 8px;
    padding: 8px;

    border-radius: 8px;
  }

  button {
    margin: 0px;
  }
</style>
