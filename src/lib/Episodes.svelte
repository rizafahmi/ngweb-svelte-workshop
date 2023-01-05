<script>
  import { onMount } from "svelte";

  let episodes = [];
  onMount(async function () {
    try {
      const res = await fetch(
        `https://youtube.googleapis.com/youtube/v3/playlistItems?part=snippet%2CcontentDetails&maxResults=25&playlistId=PLTY2nW4jwtG8Sx2Bw6QShC271PzX31CtT&key=${
          import.meta.env.VITE_APP_ACCESS_KEY
        }`
      );
      const data = await res.json();
      episodes = data.items;
      console.log(episodes);
    } catch (error) {
      console.error(error);
    }
  });
</script>

{#each episodes as episode}
  <article>
    <a
      href={"https://youtube.com/watch?v=" + episode.snippet.resourceId.videoId}
      target="_blank"
    >
      <img src={episode.snippet.thumbnails["standard"].url} />
      <h2>{episode.snippet.title}</h2>
    </a>
  </article>
{/each}
