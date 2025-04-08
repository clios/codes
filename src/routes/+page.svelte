<script>
  import Button from "$lib/components/base/button.svelte";
  import Section from "$lib/components/base/section.svelte";
  import Title from "$lib/components/base/title.svelte";
  import IconMenu from "$lib/components/icons/icon-menu.svelte";
</script>

<Section class="relative">
  <Button class="p-2 absolute top-0 right-0" size="icon" variant="ghost">
    <IconMenu />
  </Button>

  <div class="p-2">
    <p>Clios</p>
    <Title
      class="font-bold border-t border-fg w-min text-nowrap pt-4 mt-2 leading-8 pr-2"
    >
      Cliemtor Fabros
    </Title>
    <p class="text-lg text-base-500">Hey! I’m a Frontend Developer.</p>
  </div>
</Section>
