<script>
  import { MovieStore } from "../../../movie-store";

  export let data;

  let movie = $MovieStore.find((movie) => movie.id == data.id);
</script>

{#if movie}
  <p>
    {movie.title} directed by {movie.director} ({movie.year})
  </p>
{:else}
  <p>Movie not found</p>
{/if}
