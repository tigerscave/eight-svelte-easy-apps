<script>
  import SenkaiBrake from "./eachSwitchPanel/senkaiBrake.svelte";
  import IdleVolume from "./eachSwitchPanel/idleVolume.svelte";
  import SenkaiFree from "./eachSwitchPanel/senkaiFree.svelte";
  import StopSwitch from "./eachSwitchPanel/stopSwitch.svelte";
  import Mkousoku from "./eachSwitchPanel/mKousoku.svelte";
  import AmlRelease from "./eachSwitchPanel/aml.svelte";
  import Skousoku from "./eachSwitchPanel/sKousoku.svelte";
  import MakisugiKaijyo from "./eachSwitchPanel/makisugi.svelte";
</script>

<div class="handleControlPanel">
  <SenkaiBrake />
  <IdleVolume />
  <SenkaiFree />
  <StopSwitch />
  <Mkousoku />
  <AmlRelease />
  <Skousoku />
  <MakisugiKaijyo/>
</div>

<style>
  .handleControlPanel {
    display: grid;
    grid-template-columns: 1fr 1fr;
  }

</style>
