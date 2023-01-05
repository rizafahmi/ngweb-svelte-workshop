<script>
  let description = "Halo Svelte";
  $: wordCount = description.split(" ").length;
</script>

<h2>{description}</h2>
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
</style>
