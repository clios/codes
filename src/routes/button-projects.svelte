<script lang="ts">
  import Drawer from "$lib/components/base/drawer.svelte";
  import Button from "$lib/components/base/button.svelte";

  let open = $state(false);
</script>

<Button onclick={() => (open = true)}>Projects</Button>
<Drawer class="w-screen max-w-96" title="Title here" placement="left" bind:open>
  <p>Content here...</p>
</Drawer>
