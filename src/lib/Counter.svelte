<script>
  import Reset from "./Reset.svelte";

  let count = 0;
  const increment = () => {
    count += 1;
  };

  function reset() {
    count = 0;
  }
</script>

<button on:click={increment}>
  count is {count}
</button>

<Reset {reset} />
