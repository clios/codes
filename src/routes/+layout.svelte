<script lang="ts">
  import "../app.css";
  import "@fontsource-variable/nunito-sans";
  let { children } = $props();
</script>

<div class="bg-bg text-fg">
  {@render children()}
</div>
