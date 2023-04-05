<script lang="ts">
  export let count = 0;
  export let average = 0;
</script>

<div class="feedback-stats">
  <h4>{count} reviews</h4>
  <h4>{average} average</h4>
</div>

<style>
  .feedback-stats {
    display: flex;
    justify-content: space-between;
  }
</style>
