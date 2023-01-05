<script>
  let description = "Halo Svelte";
  $: wordCount = description.split(" ").length;
</script>

<h1>{description}</h1>
{#if wordCount > 5}
  <blockquote>Warning: Text too long!</blockquote>
{:else}
  <blockquote>Need more text</blockquote>
{/if}
<textarea bind:value={description} />
<p><strong>Word count: </strong>{wordCount}</p>

<style>
  blockquote {
    font-size: 2rem;
    color: tomato;
  }
  h1 {
    color: mediumaquamarine;
  }
</style>
