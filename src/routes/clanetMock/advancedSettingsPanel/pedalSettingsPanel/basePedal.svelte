<script>
  import PedalA from "./eachPedalList/pedalA.svelte";
  import PedalB from "./eachPedalList/pedalB.svelte";
  import PedalC from "./eachPedalList/pedalC.svelte";
</script>

<div class="changeSettingsContainer">
  <div>
    <p>ペダル設定</p>
  </div>
  <PedalA />
  <PedalB />
  <PedalC />
</div>

<style>
  .changeSettingsContainer {
    display: flex;
    justify-content: space-between;
  }
</style>
