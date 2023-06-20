<script>
  import { quizzes } from "./question.js";

  function checkAnswer(answer) {
    let isCorrect = quizzes.answers.indexOf(answer) === quizzes.correctAnswer;
    if (isCorrect) {
      answer = answer + "-正解！";
      answer.style.color = "green";
    } else {
      answer = answer + "-不正解…";
      answer.style.color = "red";
    }
  }
</script>

<section>
  {#each quizzes as quiz}
    <h1>{quiz.question}</h1>
    <ul>
      {#each quiz.answers as answer}
        <li  on:click={checkAnswer}>{answer}</li>
      {/each}
    </ul>
  {/each}
  <br />
  <hr />
</section>

<style>
  li {
    cursor: pointer;
    margin: 4px;
  }
</style>
