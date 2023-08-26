<script>
  let current1 = "1";
</script>

  <span class="text">ブーム・ジブ&nbsp;&emsp;選択</span>
  <span class="mainSettingsContainer">
    <button class="isSelect" class:activeYellow={current1 === "1"} on:click={() => (current1 = "1")}>1</button>
    <button class="isSelect" class:activeYellow={current1 === "2"} on:click={() => (current1 = "2")}>2</button>
    <button class="isSelect" class:activeYellow={current1 === "3"} on:click={() => (current1 = "3")}>3</button>
  </span>

<style>
  .text {
    margin-left: 3.4rem;
    margin-bottom: 3.3rem;
  }
  .mainSettingsContainer {
    font-size: 1rem;
    display: flex;
    margin-left: 3.4rem;
  }

  .isSelect {
    display: flex;
    justify-content: center;
    align-items: center;
    width: 6.3rem;
    height: 2.3rem;
    margin: 0;
    background: white;
    border: 1px solid black;
    cursor: pointer;
  }
  .activeYellow {
    background-color: yellow;
  }

</style>
