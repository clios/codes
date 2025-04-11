<script>
  import Button from "$lib/components/base/button.svelte";
  import Link from "$lib/components/base/link.svelte";
  import Text from "$lib/components/base/text.svelte";
  import Title from "$lib/components/base/title.svelte";
  import IconGithub from "$lib/components/icons/icon-github.svelte";
  import Design_001 from "$lib/components/tiles/design-001.svelte";
  import { onMount } from "svelte";
  import ButtonProjects from "./button-projects.svelte";
  import ButtonToggleMode from "./button-toggle-mode.svelte";
  import { twMerge } from "tailwind-merge";

  let animate = $state(false);

  onMount(() => {
    setTimeout(() => {
      animate = true;
    }, 1000);
  });
</script>

<div
  class={twMerge(
    "bg-gradient-to-b from-fg/5 via-bg to-fg/5 p-2 sm:p-4 md:p-8 lg:p-16 w-screen h-screen grid place-self-center opacity-0 duration-500",
    animate && "opacity-100"
  )}
>
  <Design_001
    class={twMerge(
      "transition-all w-0 h-0 m-auto overflow-clip duration-1000 delay-500",
      animate && "w-full h-full animate-none"
    )}
  >
    <div class="relative grid p-2 sm:p-4 md:p-8 lg:p-16 h-full">
      <div
        class={twMerge(
          "w-0 flex justify-between items-center border-b h-min delay-1000 transition-all opacity-0 duration-500",
          animate && "w-full opacity-100"
        )}
      >
        <Link class="flex items-center pt-1 text-fg">
          <IconGithub class="inline text-primary" />
          <Text class="text-border font-mono">{`/`}</Text>
          <Text>clios</Text>
        </Link>
        <!-- BUTTON TOGGLE MODE -->
        <ButtonToggleMode />
      </div>

      <div
        class={twMerge(
          "h-0 transition-all opacity-0 delay-1500 duration-500",
          animate && "opacity-100 h-full"
        )}
      >
        <Title class="font-bold text-3xl">Cliemtor Fabros</Title>
        <Text class="text-base-500">Hey! I’m a Frontend Developer.</Text>

        <div class="flex gap-2 mt-4">
          <ButtonProjects />
          <Button variant="inverted">Contacts</Button>
          <Button variant="inverted">Bio</Button>
        </div>
      </div>

      <div
        class={twMerge(
          "w-0 flex flex-col justify-end self-end transition-all duration-500 delay-2000 opacity-0",
          animate && "w-full opacity-100"
        )}
      >
        <Text class="text-right italic text-base-500 w-full">
          clios1208@gmail.com
        </Text>
        <Text class="text-right border-t w-full text-border font-mono">
          /////////////////<span class="text-primary">////////</span>
        </Text>
      </div>
    </div>
  </Design_001>
</div>
