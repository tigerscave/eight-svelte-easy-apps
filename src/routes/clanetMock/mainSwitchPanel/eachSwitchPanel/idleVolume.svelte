<script>
  let current = ''
</script>

<div class="handleControlContainer">
  アイドル&shy;ボリューム
  <span class="handleControlSwitch">
    <button   class:activeYellow={current === "↑"}
    on:mousedown={() => (current = "↑")} on:mouseup={() => (current = "")}>↑</button>
    <button class:activeYellow={current === "↓"}
    on:mousedown={() => (current = "↓")} on:mouseup={() => (current = "")}>↓</button>
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

  .handleControlSwitch {
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
    justify-content: center;
    align-items: center;
    cursor: pointer;
  }

  .activeYellow {
    background-color: yellow;
  }
</style>