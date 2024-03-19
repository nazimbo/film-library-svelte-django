<script>
  import { MovieStore } from "../../movie-store";

  let handleClick = () =>
    MovieStore.update((movies) => {
      let newMovie = {
        id: 4,
        title: "The Room",
        year: 2003,
        director: "Tommy Wiseau",
        cast: ["Tommy Wiseau", "Juliette Danielle", "Greg Sestero"],
      };
      return [...movies, newMovie];
    });
</script>

<h1>Movies</h1>
<ul>
  {#each $MovieStore as movie}
    <li>
      <a href="movies/{movie.id}">{movie.title} </a>
    </li>
  {/each}
</ul>

<button on:click={handleClick}>Add a movie</button>
