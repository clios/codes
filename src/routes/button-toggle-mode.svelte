<script lang="ts">
    import Button from "$lib/components/base/button.svelte";
    import IconMoon from "$lib/components/icons/icon-moon.svelte";
    import IconSun from "$lib/components/icons/icon-sun.svelte";
    import { toggleMode, mode } from "mode-watcher";
</script>

<Button onclick={toggleMode} size="icon" variant="ghost">
    {#if $mode === "dark"}
        <IconMoon />
    {:else}
        <IconSun />
    {/if}
</Button>
