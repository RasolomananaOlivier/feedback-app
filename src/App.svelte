<script lang="ts">
  let a = 1;
  let b = 1;

</script>

<main>
  <input type="number" bind:value={a}>
  <input type="number" bind:value={b}>

  {a} + {b} = {a + b}
</main>

