<script>
  import Lever2 from "./eachLeverList/lever2.svelte";
  import Lever3 from "./eachLeverList/lever3.svelte";
  import Lever4 from "./eachLeverList/lever4.svelte";
  import Lever5 from "./eachLeverList/lever5.svelte";
</script>

<div class="changeSettingsContainer">
  <div>
    <p>レバー設定</p>
  </div>
  <Lever2 />
  <Lever3 />
  <Lever4 />
  <Lever5 />
</div>

<style>
  .changeSettingsContainer {
    display: flex;
    justify-content: space-between;
  }
</style>
