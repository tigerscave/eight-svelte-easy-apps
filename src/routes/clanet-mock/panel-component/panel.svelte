<script>
  let activeRed = false; //初期値をOFF
  let activeBlue = false; //初期値をOFF

  function switchBreakOn(buttonLeft) {
    if (buttonLeft == false) {
      activeRed = !activeRed; //ONのまま
    } else {
      activeRed = false;
    }
  }
  function switchBreakOff(activeBlue) {
    if (activeBlue == false) {
      activeBlue = !activeBlue; //値をONにする。
    } else {
      activeBlue = false;
    }
  }
</script>

<div class="handleControlContainer">
  旋回ブレーキ
  <span class="handleControlSwitch-ON">
    <button
      type="buttonLeft"
      on:click={switchBreakOn}
      class:activeRed={activeRed === false}
>ON</button
    >
    <button
      type="buttonRight"
      on:click={switchBreakOff}
   
      class:activeRed={activeRed === true}>OFF</button
    >
  </span>
</div>

<style>
  .handleControlContainer {
    margin-top: 1.8em;
    margin-left: 1.5em;
    display: flex;
    align-items: center;
    justify-content: space-between;
  }

  .handleControlSwitch-ON {
    margin-right: 6%;
    font-size: 1rem;
    display: flex;
  }

  button {
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
