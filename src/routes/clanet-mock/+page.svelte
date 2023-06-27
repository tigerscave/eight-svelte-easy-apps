<script>
import Panel from "./panel-component/panel.svelte";
import Lever from "./lever.svelte";
import Settings from "./settings.svelte";
</script>

<body>
  <div class="touchPanel">
    <div class="touchPanelTitle">CRANET&nbsp;&emsp;集約タッチパネル&nbsp;&emsp;v2.0</div>
    <Panel />
    <Lever />
    <Settings />
  </div>
</body>

<style>

.touchPanel {
  margin-bottom: 0.5em;
  border: 1px solid black;
  padding: 1.2em 1.2em 2.4em;
  background: #e7eaeb;
  width: 7.5in;
  height: 11.1in;
}

.touchPanelTitle {
  margin-bottom: 1.1em;
  margin-left: 1em;
  margin-top: 1em;
  font-size: 1.2rem;
}

</style>