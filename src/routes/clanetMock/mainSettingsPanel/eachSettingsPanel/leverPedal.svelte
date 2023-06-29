<script>
  let currentIso = "ISO";
  let displayBaseSettingsPanel = false;
  
  function handleClick() {
    currentIso = "カスタム";
    displayBaseSettingsPanel = !displayBaseSettingsPanel;
  }

</script>

  <span class="text">レバー・ペダル 配列</span>
  <span class="mainSettingsContainer">
    <button class="isSelect" class:activeYellow={currentIso === "ISO"} on:click={() => (currentIso = "ISO")}>ISO</button>
    <button class="isSelect" class:activeYellow={currentIso === "タダノ"} on:click={() => (currentIso = "タダノ")}>タダノ</button>
    <button class="isSelect"class:activeYellow={currentIso === "カスタム"} on:click={handleClick}>カスタム</button>
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
