<script>

  const quizzes = [
    {
      question: "①出身地は？",
      answers: ["愛知県", "高知県", "山口県"],//[]で囲むのが、配列のリテラル表現
      correctAnswer: 0,
    },
    {
      question: "②好きな動物は？",
      answers: ["Tigers", "Doragons", "Giants"],
      correctAnswer: 1,
    },
    {
      question: "③好きな音楽は？",
      answers: ["Country", "Classic", "Heavy Metal"],
      correctAnswer: 0,
    },
    {
      question: "④好きなアニメは？",
      answers: ["マジンガーZ", "未来少年コナン", "アルプスの少女ハイジ"],
      correctAnswer: 1,
    },
  ];

  function checkAnswer(answer) {
    let isCorrect = quizzes.answers === quizzes.correctAnswer;

    if(isCorrect) {
      answer = answer + '-正解！';
      answer.style.color = green;
    }
    else {
      answer = answer + '-不正解…';
      answer.style.color = red;
    }
  }

</script>

<body>
  <main>
    <h1>三択クイズ</h1>
    <section>
      {#each quizzes as quiz}
        <h1>{quiz.question}</h1>
        <ul>
          {#each quiz.answers as answer}
            <li on:click={checkAnswer}>{answer}</li>
          {/each}
        </ul>
      {/each}
      <hr />
    </section>
  </main>
</body>

<style>
  main {
    width: 320px;
    margin: 32px auto 0;
  }

  h1 {
    font-size: 20px;
    text-align: center;
    border-bottom: 1px solid #ccc;
    padding-bottom: 8px;
  }

  li {
    cursor: pointer;
    margin: 4px;
  }
</style>
