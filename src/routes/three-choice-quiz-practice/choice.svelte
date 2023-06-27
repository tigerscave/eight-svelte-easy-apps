<script>
  export let word
  export let correctAnswer

  let isCorrect;

  function checkAnswer(word) {
    console.log(word)
    console.log(correctAnswer)
    if(word === correctAnswer) {
      isCorrect = true
    } else {
      isCorrect = false
    }
  }
</script>

<li
  on:click|once={checkAnswer(word)}
  class:correct="{isCorrect === true}"
  class:wrong="{isCorrect === false}"
>
  {word}
  {#if isCorrect === true} CORRECT
  {:else if isCorrect === false} WRONG
  {/if}
</li>

<style>
li {
    cursor: pointer;
    margin: 4px;
  }
  
  .correct {
    color: red;
  }

  .wrong {
    color: blue;
  }
</style>