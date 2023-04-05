<script lang="ts">
  import FeedbackItem from "./FeedbackItem.svelte";

  export let feedbacks: Feedback[] = [];
</script>

<div>
  <h1>List of feedbacks.</h1>
  {#each feedbacks as feedback (feedback.id)}
    <FeedbackItem {feedback} on:delete-feedback />
  {/each}
</div>
