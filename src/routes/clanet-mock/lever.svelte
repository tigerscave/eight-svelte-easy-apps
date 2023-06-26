<div class="handleControlPanel2">
  <span class="text">ブーム・ジブ&nbsp;&emsp;選択</span>
  <span class="select-container">
    <button type="button" class="isSelect">1</button>
    <button type="button" class="isSelect">2</button>
    <button type="button" class="isSelect">3</button>
  </span>
  <span class="text">レバー・ペダル 配列</span>
  <span class="select-container">
    <button type="button" id="iso-button" class="isSelect">ISO</button>
    <button type="button" id="tadano-button" class="isSelect">タダノ</button>
    <button type="button" id="custom-button" class="isSelect">カスタム</button>
  </span>
</div>

<style>
  .handleControlPanel2 {
    display: grid;
    grid-template-columns: 1fr 1fr;
    margin-top: 3.3rem;
  }

  .handleControlPanel3 {
    display: flex;
  }

  .text {
    margin-left: 3.4rem;
    margin-bottom: 3.3rem;
  }
  .select-container {
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

</style>
