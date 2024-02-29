<script>
  import { MovieStore } from "../../movie-store";
</script>

<h1>Movies</h1>
<ul>
  {#each $MovieStore as movie}
    <li>
      <a href="movies/{movie.id}">{movie.title} </a>- {movie.year}
    </li>
  {/each}
</ul>
