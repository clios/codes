<script lang="ts">
  import "../app.css";
  import "@fontsource-variable/nunito-sans";
  import { ModeWatcher } from "mode-watcher";
  let { children } = $props();
</script>

<ModeWatcher defaultMode="system" />
<div class="bg-bg text-fg bg-gradient-to-b from-fg/5 via-bg to-fg/5">
  {@render children()}
</div>
