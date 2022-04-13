<script>
  import { createEventDispatcher } from "svelte";
  const dispatch = createEventDispatcher();
  export let searchTerm;
</script>

<div>
  <h4>
    {#if searchTerm}for{/if}
  </h4>
  {searchTerm}
  <input
    type="text"
    aria-label="Search Input"
    bind:value={searchTerm}
    on:keyup={() => {
      dispatch("updateSearch");
    }}
  />
</div>
