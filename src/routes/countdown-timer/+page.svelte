<script>
  import { onMount, onDestroy } from 'svelte';

  const totalSeconds = Math.floor(countdown / 1000); //Math.floorで小数を切り捨て。1000で割って、ミリ秒→秒単位で表示する。
  const minutes = Math.floor(totalSeconds / 60); //0〜99秒を60で割って、余りを分単位で表示する。
  const seconds = totalSeconds % 60; //0〜99秒を60で割って、余りを0〜59秒単位で表示する。

  const minutesFormatted = String(minutes).padStart(2, "0"); //00〜59分の間の分単位で表示する。
  const secondsFormatted = String(seconds).padStart(2, "0"); //00〜59秒の間の秒単位で表示する。今回は03秒からスタート。

  function handleClick() {//ボタンが押されたときの処理
    onMount(() => {
      let restTime = new Date().getTime() + 3 * 1000; //残り時間を３秒と定義する
      let countdown = restTime - new Date().getTime(); //残り時間から現在時刻を引いて、カウントダウンを行う。
      btn.disabled = true; //カウントダウン中は、ボタンをdisaledにする。
      btn.classList.add("inactive"); // カウントダウン中は、inactiveにする。
      return countdown; //カウントダウン中の値を返す。
    });
  }
  
  let zeroTime = restTime === new Date().getTime(); // 残り時間が0になったときの定義

  onDestroy(() => {
    clearInterval(zeroTime); //カウントダウンが０になったら、３に戻る処理を行う。
    btn.disabled = false; //ボタンを有効化する。
    btn.classList.remove("inactive"); //inactive要素を取り除く。
  });
</script>

<body>
  <main>
    <p>{minutesFormatted}:{secondsFormatted}</p>
    <button id="btn" on:click={handleClick}>Start</button>
  </main>
</body>

<style>
  body {
    background: #e6f6ff;
  }

  p {
    margin: 0;
    background: #ddd;
    padding: 32px 0;
    font-size: 40px;
    font-family: "Courier New";
  }

  main {
    background: #fff;
    width: 320px;
    margin: 16px auto 0;
    text-align: center;
    padding: 16px;
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

  .inactive {
    background: #ddd;
    color: #444;
    cursor: default;
  }
  .inactive:hover {
    opacity: 1;
  }
</style>
