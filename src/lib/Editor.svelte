<script>
  let description = "Halo Svelte";
  $: wordCount = description.split(" ").length;
</script>

<h2>{description}</h2>
<textarea bind:value={description} />
<p><strong>Word count: </strong>{wordCount}</p>
