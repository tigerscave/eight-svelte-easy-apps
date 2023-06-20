<script>
  import Question from "./question.svelte";
</script>

<body>
  <main>
    <h1>三択クイズ</h1>
    <Question />
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
</style>
