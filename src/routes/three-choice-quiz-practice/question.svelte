<script>
  import { quizzes } from "./question.js";

  function checkAnswer(ans) {
    console.log(quizzes);

    //1問目のクイズ
    if (ans == quizzes[0].answers[0]) {
      quizzes[0].answers[0] = quizzes[0].answers[0] + "-正解";
      console.log(quizzes[0].answers[0].style)
      quizzes[0].answers[0].style.color = "green";
    } else if (ans == quizzes[0].answers[1]) {
      quizzes[0].answers[1] = quizzes[0].answers[1] + "-不正解";
    } else if (ans == quizzes[0].answers[2]) {
      quizzes[0].answers[2] = quizzes[0].answers[2] + "-不正解";
    } else if (ans == quizzes[1].answers[0]) {
      //2問目のクイズ
      quizzes[1].answers[0] = quizzes[1].answers[0] + "-不正解";
    } else if (ans == quizzes[1].answers[1]) {
      quizzes[1].answers[1] = quizzes[1].answers[1] + "-正解";
    } else if (ans == quizzes[1].answers[2]) {
      quizzes[1].answers[2] = quizzes[1].answers[2] + "-不正解";
      //3問目のクイズ
    } else if (ans == quizzes[2].answers[0]) {
      quizzes[2].answers[0] = quizzes[2].answers[0] + "-正解";
    } else if (ans == quizzes[2].answers[1]) {
      quizzes[2].answers[1] = quizzes[2].answers[1] + "-不正解";
    } else if (ans == quizzes[2].answers[2]) {
      quizzes[2].answers[2] = quizzes[2].answers[2] + "-不正解";
      //4問目のクイズ
    } else if (ans == quizzes[3].answers[0]) {
      quizzes[3].answers[0] = quizzes[3].answers[0] + "-不正解";
    } else if (ans == quizzes[3].answers[1]) {
      quizzes[3].answers[1] = quizzes[3].answers[1] + "-正解";
    } else if (ans == quizzes[3].answers[2]) {
      quizzes[3].answers[2] = quizzes[3].answers[2] + "-不正解";
      quizzes[3].answers[2].style.color = "#2C81B7";
    }
  }
</script>

<section>
  {#each quizzes as quiz}
    <h1>{quiz.question}</h1>
    <ul>
      {#each quiz.answers as ans}
        <li on:click|once={checkAnswer(ans)}>{ans}</li>
      {/each}
    </ul>
  {/each}
  <hr />
</section>

<style>
  li {
    cursor: pointer;
    margin: 4px;
  }
  .corre {
  color: green;
}
  .wrong {
  color: red;
}
</style>
