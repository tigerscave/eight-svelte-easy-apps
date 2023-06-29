<script>
  import Choice from "./choice.svelte";
  export let quiz; // props
</script>

<section>
  <p>{quiz.question}</p>
  <ul>
    {#each quiz.answers as answer}
      <Choice word={answer} correctAnswer={quiz.answers[quiz.correctAnswer]} />
    {/each}
  </ul>
</section>
