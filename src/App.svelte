<script>
  import { onMount } from "svelte";
  import CastList from "./CastList.svelte";
  import CastSearch from "./CastSearch.svelte";
  let searchTerm = "";
  let cast = [];
  let castList = [];
  function filterList(list, query) {
    return list.filter((item) => {
      return item.name.toLowerCase().match(query.toLowerCase());
    });
  }

  onMount(async () => {
    const res = await fetch(`cast.json`);
    cast = await res.json();
    castList = cast;
  });
</script>

<main class="container">
  <CastSearch
    bind:searchTerm
    on:updateSearch={() => {
      castList = filterList(cast, searchTerm);
    }}
  />
  <CastList cast={castList} />
</main>
