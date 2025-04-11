<script>
  import Button from "$lib/components/base/button.svelte";
  import Link from "$lib/components/base/link.svelte";
  import Text from "$lib/components/base/text.svelte";
  import Title from "$lib/components/base/title.svelte";
  import IconGithub from "$lib/components/icons/icon-github.svelte";
  import Design_001 from "$lib/components/tiles/design-001.svelte";
  import ButtonToggleMode from "./button-toggle-mode.svelte";
</script>

<div
  class="bg-gradient-to-b from-fg/5 via-bg to-fg/5 p-2 sm:p-4 md:p-8 lg:p-16 w-screen h-screen"
>
  <Design_001 class="w-full h-full">
    <div class="relative grid p-2 sm:p-4 md:p-8 lg:p-16 h-full">
      <div class="flex justify-between items-center border-b h-min">
        <Link class="flex items-center pt-1 text-fg">
          <IconGithub class="inline text-primary" />
          <Text class="text-border font-mono">{`/`}</Text>
          <Text>clios</Text>
        </Link>
        <!-- BUTTON TOGGLE MODE -->
        <ButtonToggleMode />
      </div>

      <div class="h-full">
        <Title class="font-bold text-3xl">Cliemtor Fabros</Title>
        <Text class="text-base-500">Hey! I’m a Frontend Developer.</Text>

        <div class="flex gap-2 mt-2">
          <Button>Bio</Button>
          <Button>Contact</Button>
          <Button>Projects</Button>
        </div>
      </div>

      <div class="flex justify-end self-end border-t">
        <Text class="text-border font-mono">
          /////////////////<span class="text-primary">////////</span>
        </Text>
      </div>
    </div>
  </Design_001>
</div>
