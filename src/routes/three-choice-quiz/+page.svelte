<script>
  const quizzes = [
    {
      question: "①出身地は？",
      choices: ['愛知県', '高知県', '山口県',],
      answerIndex: 0
    },
    {
      question: "hoge",
      choices: ['fuga', 'piyo', 'bar',],
      answerIndex: 1
    },
  ];
  let correctAnswer = '-正解😆'
  let wrongAnswer = '-不正解…😖'

  let firstValue =''
  let secondValue = ''
  let thirdValue = ''

</script>

<body>
  <main>
    <h1>三択クイズ</h1>
    <section>
      {#each quizzes as quiz}
        <h1>{quiz.question}</h1>
        <ul>
          {#each quiz.choices as choice}
            <li>{choice}</li>
          {/each}
        </ul>
      {/each}

      <hr/>
      <h2>①出身地は？</h2>
      <ul>
        {#each quizzes[0] as quiz}
          <li>{quiz}</li>
        {/each}
      </ul>
      
      <ul>
        <li on:click|once={() => firstValue = correctAnswer}>愛知県{firstValue}</li>
        <li on:click|once={() => secondValue = wrongAnswer}>山口県{secondValue}</li>
        <li on:click|once={() => thirdValue = wrongAnswer}>高知県{thirdValue}</li>
      </ul>
      <h2>②好きな動物は？</h2>
      <ul>
        <li>ホッキョクグマ</li>
        <li>キリン</li>
        <li>マンドリル</li>
      </ul>
      <h2>③好きな音楽は？</h2>
      <ul>
        <li>スピッツ</li>
        <li>大塚愛</li>
        <li>神聖かまってちゃん</li>
      </ul>
      <h2>④好きな偉人は？</h2>
      <ul>
        <li>織田信長</li>
        <li>福沢諭吉</li>
        <li>やなせたかし</li>
      </ul>
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

h2 {
  font-size: 16px;
  margin-bottom: 4px;
}

li {
  cursor: pointer;
  margin: 4px;
}

.correct {
  color: green;
}
.changeCorrectColor {
  color: green;
}

.correct::after {
  content: ' - 正解！';
}

.wrong {
  color: red;
}

.wrong::after {
  content: ' - 不正解...';
}
.correctColor {
  color: green;
}

</style>