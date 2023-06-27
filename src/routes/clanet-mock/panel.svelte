<script>
  let activeRed = false; //初期値をOFF
  let activeBlue = false; //初期値をOFF

  function switchBreakOn() {
    if (activeRed == false) {
      //スイッチがOFFのとき
      activeRed == !activeRed; //値をONにする。
      console.log(false);
    } else {
      //スイッチが既にONのときは、何もしない。
    }
  }

  function switchBreakOff() {
    if (activeBlue == false) {
      //スイッチがOFFのとき
      activeBlue == !activeBlue; //値をONにする。
    } else {
    }
  }
</script>

<div class="handleControlPanel">
  <div class="handleControlContainer">
    旋回ブレーキ
    <span class="handleControlSwitch-ON">
      <button
        type="button"
        on:click={switchBreakOn}
        class={!activeRed ? "activeRed" : ""}>ON</button
      ><!--スイッチの初期値ONにする-->
      <button
        type="button"
        on:click={switchBreakOff}
        class={!activeBlue ? "" : "activeBlue"}>OFF</button
      >
    </span>
  </div>
  <div class="handleControlContainer">
    アイドル&shy;ボリューム
    <span class="handleControlSwitch-SP">
      <button type="button" class="switch-up">↑</button>
      <button type="button" class="switch-down">↓</button>
    </span>
  </div>
  <div id="rotation-free-button" class="handleControlContainer">
    旋回フリー
    <span class="handleControlSwitch">
      <button type="button">ON</button>
      <button type="button">OFF</button>
    </span>
  </div>
  <div class="handleControlContainer">
    ストップ&shy;スイッチ
    <span class="handleControlSwitch">
      <button type="button">ON</button>
      <button type="button">OFF</button>
    </span>
  </div>
  <div class="handleControlContainer">
    M高速巻下
    <span class="handleControlSwitch">
      <button type="button">ON</button>
      <button type="button">OFF</button>
    </span>
  </div>
  <div class="handleControlContainer">
    AML解除
    <span class="handleControlSwitch">
      <button type="button">ON</button>
      <button type="button">OFF</button>
    </span>
  </div>
  <div class="handleControlContainer">
    S高速巻下
    <span class="handleControlSwitch">
      <button type="button">ON</button>
      <button type="button">OFF</button>
    </span>
  </div>
  <div class="handleControlContainer">
    巻き過&nbsp;&emsp;解除
    <div class="circle"><span>解除</span></div>
  </div>
</div>

<style>
  .handleControlPanel {
    display: grid;
    grid-template-columns: 1fr 1fr;
  }

  .handleControlContainer {
    margin-top: 1.8em;
    margin-left: 1.5em;
    display: flex;
    align-items: center;
    justify-content: space-between;
  }

  .circle {
    position: absolute;
    left: 39rem;
    width: 60px;
    height: 60px;
    background: white;
    border: 1px solid black;
    border-radius: 50%;
    display: flex;
    align-items: center;
    justify-content: center;
  }

  .circle span {
    writing-mode: vertical-rl;
    color: black;
  }

  .handleControlSwitch {
    margin-right: 6%;
    font-size: 1rem;
    display: flex;
  }

  .handleControlSwitch-ON,
  .handleControlSwitch-SP {
    margin-right: 6%;
    font-size: 1rem;
    display: flex;
  }

  button,
  .switch-on,
  .switch-off,
  .switch-up,
  .switch-down {
    width: 4.6rem;
    height: 2.3rem;
    margin: 0;
    background: white;
    border: 1px solid black;
    display: flex;
    justify-content: center;
    align-items: center;
  }
  .activeRed {
    background-color: red;
  }
  .activeBlue {
    background-color: blue;
  }
</style>
