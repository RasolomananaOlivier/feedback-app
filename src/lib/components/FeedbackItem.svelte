<script lang="ts">
  import Card from "./Card.svelte";
  import dayjs from "dayjs";
  import RelativeTime from "dayjs/plugin/relativeTime";
  import { createEventDispatcher } from "svelte";
  dayjs.extend(RelativeTime);

  export let feedback: Feedback;

  const dispatch = createEventDispatcher();
  function handleClick() {
    dispatch("delete-feedback", { id: feedback.id });
  }
</script>

<div>
  <Card>
    <div class="feedback-container">
      <p class="feedback-rating">{feedback.rating}</p>
      <div>
        <h3 class="feedback-comment">{feedback.comment}</h3>
        <p class="feedback-createdAt">
          {dayjs(feedback.createdAt).fromNow()}
        </p>

        <div class="feedback-delete-container">
          <button on:click={handleClick}> Delete </button>
        </div>
      </div>
    </div>
  </Card>
</div>

<style>
  .feedback-container {
    display: flex;
    position: relative;
    padding-left: 2rem;
  }

  .feedback-rating {
    font-size: 2rem;
    font-weight: bold;
    margin-right: 1.5rem;

    position: absolute;
    top: -4rem;
    left: -1.5rem;
    background-color: #e04f4f;
    color: white;
    width: 3rem;
    height: 3rem;
    border-radius: 50%;
  }

  .feedback-comment,
  .feedback-createdAt {
    text-align: start;
  }
  .feedback-createdAt {
    font-size: 0.9rem;
    color: #666;
  }

  .feedback-delete-container {
    display: flex;
    justify-content: flex-start;
  }
</style>
