<script>
  let currentOff = "OFF";
</script>

<div class="handleControlContainer">
  M高速巻下
  <span class="handleControlSwitch">
    <button class:activeRed={currentOff === "ON"} on:click={() => (currentOff = "ON")}>ON</button>
    <button class:activeBlue={currentOff === "OFF"} on:click={() => (currentOff = "OFF")}>OFF</button>
  </span>
</div>

<style>
  .handleControlSwitch {
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
