<script>
  export let cast;
</script>

<div class="group">
  {#each cast as { name, slug }}
    <div class="item">
      <img src={`/images/${slug}_tn.svg`} alt={name} />
      <h4>{name}</h4>
    </div>
  {/each}
</div>

<style>
  .group {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    width: 100%;
  }
  .item {
    display: flex;
    border-bottom: 1px dotted rgba(110, 110, 110, 0.4);
    padding: 10px;
    width: 300px;
    gap: 10px;
  }
  img {
    width: 70px;
    border-radius: 50%;
    background-color: dodgerblue;
  }
  h4 {
    align-self: center;
    margin-bottom: 0;
  }
</style>
