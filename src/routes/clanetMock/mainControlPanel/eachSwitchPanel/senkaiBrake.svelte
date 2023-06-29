<script>
  let currentOn = "ON";
</script>

<div class="handleControlContainer">
  旋回ブレーキ
  <span class="handleControlSwitch-ON">
    <button class:activeRed={currentOn === "ON"} on:click={() => (currentOn = "ON")}>ON</button>
    <button class:activeBlue={currentOn === "OFF"} on:click={() => (currentOn = "OFF")}>OFF</button>
  </span>
</div>

<style>
  .handleControlSwitch-ON {
    margin-right: 6%;
    display: flex;
  }
  .handleControlContainer {
    margin-top: 1.8em;
    margin-left: 1.5em;
    display: flex;
    align-items: center;
    justify-content: space-between;
  }

  button {
    width: 4.6rem;
    height: 2.3rem;
    margin: 0;
    background: white;
    border: 1px solid black;
    cursor: pointer;
  }

  .activeRed {
    background-color: red;
  }

  .activeBlue {
    background-color: blue;
  }
</style>
