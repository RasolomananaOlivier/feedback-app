<script lang="ts">
  import FeedbackList from "./lib/components/FeedbackList.svelte";

  let feedbacks: Feedback[] = [
    {
      id: "1",
      comment: "This is a test feedback",
      rating: 5,
      createdAt: new Date("2023-01-01"),
    },
    {
      id: "2",
      comment: "This is a test feedback",
      rating: 8,
      createdAt: new Date("2023-04-05"),
    },
  ];

  function deleteFeedback(e) {
    const feedbackId = e.detail.id;
    feedbacks = feedbacks.filter((feedback) => feedback.id !== feedbackId);
  }
</script>

<main>
  <FeedbackList {feedbacks} on:delete-feedback={deleteFeedback} />
</main>
