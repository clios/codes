<script lang="ts">
  import "../app.css";
  import "@fontsource-variable/nunito-sans";
  import { ModeWatcher } from "mode-watcher";
  let { children } = $props();
</script>

<ModeWatcher defaultMode="system" />
<div class="bg-bg text-fg">
  {@render children()}
</div>
