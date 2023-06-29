<script>
  let current = ''
</script>


<div class="handleControlContainer">
  巻き過&nbsp;&emsp;解除
  <div class="circle" class:activeYellow={current === "解除"}
  on:mousedown={() => (current = "解除")} on:mouseup={() => (current = "")}><span>解除</span></div>
</div>

<style>
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
    cursor: pointer;
  }

  .circle span {
    writing-mode: vertical-rl;
    color: black;
  }

  .activeYellow {
    background-color: yellow;
  }
</style>
