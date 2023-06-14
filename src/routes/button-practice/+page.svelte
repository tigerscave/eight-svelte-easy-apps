<script>
  
//カウントダウン機能に必要な定義
  let countDownValue = 3;
  let isCountingDown = true;

  function toggleCountingDown() {
    isCountingDown = !isCountingDown;
  }
  function countDownTimer() {
    setInterval(() => {
      count--;
    }, 1000)
  }
  //カウントアップ機能に必要な定義
  let isCounting = true; 
  let count = 0;
  let timerId;

  //カウントアップの処理
  function toggleCounting() {
    isCounting = !isCounting;
  }

  function startTimer() {
    timerId = setInterval(() => {
      count++;
      // console.log(count)
    }, 1000)
    toggleCounting()
  }
  
  function stopTimer() {
    clearInterval(timerId)
    toggleCounting()
  }

</script>

<body>
  <main>
    <div>カウントダウン↓</div>
    <p>{countDownValue}</p>
    {#if isCountingDown}
      <button disabled={!isCountingDown} on:click={toggleCountingDown}>Start</button>
    {:else}
      <button id="btn" disabled={isCountingDown} on:click={toggleCountingDown}>...Wait</button>
    {/if}
    <br>
    <br>
    <div>カウントアップ</div>
    <p>{count}</p>
    {#if isCounting}
    <button on:click={startTimer}>START TIMER</button>
    {:else }
    <button on:click={stopTimer}>STOP!!</button>
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
</style>
