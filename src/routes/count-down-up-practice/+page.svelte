<script>
  //２つのアプリに共通して必要な定義
  let timerId;

  //カウントダウン機能に必要な定義
  let countDownInitValue = 3;
  let isCountingDown = true;

  function toggleCountingDown() {
    isCountingDown = !isCountingDown;
  }
  function startCountDowntimer() {
    timerId = setInterval(() => {
      countDownInitValue--;
      // console.log(count)
    }, 1000);
    toggleCountingDown();
  }

  //$: 変数の値の変化に応じて、自動的に処理を行う。今回は、値が0未満の条件時に、実行する。
  $: {
    if (countDownInitValue < 0) {
      clearInterval(timerId); // 値が0未満になったら、ループを終える。
      countDownInitValue = 3; //初期値を3に設定する。
    }
  }

  //カウントアップ機能に必要な定義
  let isCountingUp = true;
  let count = 0;

  //カウントアップの処理
  function toggleCountingUp() {
    isCountingUp = !isCountingUp;
  }

  function startCountUptimer() {
    timerId = setInterval(() => {
      count++;
    }, 1000);
    toggleCountingUp();
  }

  function stopCountUpTimer() {
    clearInterval(timerId);
    toggleCountingUp();
  }
</script>

<body>
  <main>
    <div>カウントダウン↓</div>
    <p>{countDownInitValue}</p>
    {#if countDownInitValue === 3}
      <button on:click|once={startCountDowntimer}>Start</button>
    {:else}
      <button class:bg-gray={0 <= countDownInitValue < 3} disabled
        >...Wait</button
      >
    {/if}
    <br />
    <br />
    <div>カウントアップ</div>
    <p>{count}</p>
    {#if isCountingUp}
      <button on:click={startCountUptimer}>START TIMER</button>
    {:else}
      <button on:click={stopCountUpTimer}>STOP!!</button>
    {/if}
  </main>
</body>

<style>
  body {
    background: #e6f6ff;
  }
  main {
    background: #fff;
    width: 320px;
    margin: 16px auto 0;
    text-align: center;
    padding: 16px;
  }
  p {
    margin: 0;
    background: #ddd;
    padding: 32px 0;
    font-size: 40px;
    font-family: "Courier New";
  }
  button {
    all: unset;
    width: 100%;
    background: #08c;
    color: #fff;
    font-weight: bold;
    padding: 16px 0;
    margin-top: 16px;
    cursor: pointer;
  }

  button:hover {
    opacity: 0.6;
  }

  button:active {
    opacity: 0.4;
  }

  .bg-gray {
    background-color: gray;
  }
</style>
