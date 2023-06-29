<script>
  import BaseLever from "./leverSettingsPanel/baseLever.svelte";
  import BasePedal from "./pedalSettingsPanel/basePedal.svelte";

  let custom = { edit: false };

  function customEditToggle() {
    custom.edit = !custom.edit;
  }
</script>
<!-- {#if displayBaseSettingsPanel} レバーペダル配列のカスタムボタンが押されたら、-->
<div class="displayBaseSettingsPanel">
    <BaseLever />
    <BasePedal />
  {#if custom.edit}
    <div class="saveBox">
      <button on:click={customEditToggle} class="edit-settings">カスタム設定を編集</button>
    </div>
  {:else}
    <div class="saveBox">
      <button on:click={customEditToggle} class="edit-settings">カスタム設定を保存</button>
    </div>
  {/if}
</div>
<!-- {/if} -->

<style>
  .saveBox {
    display: flex;
    justify-content: center;
    align-items: center;
  }

  .edit-settings {
    width: 11rem;
    height: 2.3rem;
    margin-top: 2rem;
    background: white;
    border: 1px solid black;
    cursor: pointer;
  }

  button:active {
    transform: translateY(1px);
  }

</style>
