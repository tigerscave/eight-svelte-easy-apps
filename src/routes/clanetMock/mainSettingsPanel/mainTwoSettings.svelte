<script>
  import BoomJib from "./eachSettingsPanel/boomJib.svelte";
  import LeverPedal from "./eachSettingsPanel/leverPedal.svelte";
</script>

<div class="mainSettingsPanel">
  <BoomJib />
  <LeverPedal />
</div>

<style>
  .mainSettingsPanel {
    display: grid;
    grid-template-columns: 1fr 1fr;
    margin-top: 3.3rem;
  }
</style>
