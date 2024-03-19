<script>
  import { goto } from "$app/navigation";
  import { MovieStore } from "../../../movie-store";

  let title = "";
  let director = "";

  let handleSubmit = () => {
    MovieStore.update((movies) => {
      let id = movies[movies.length - 1].id + 1;
      let newMovie = {
        id: id,
        title: title,
        director: director,
      };
      return [...movies, newMovie];
    });
    goto("/movies");
  };
</script>

<h1>Add a movie</h1>
<form on:submit|preventDefault={handleSubmit}>
  <div>
    <input type="text" placeholder="title" bind:value={title} />
  </div>

  <div>
    <input type="text" placeholder="director" bind:value={director} />
  </div>

  <button class="submit">Add</button>
</form>
