<script>
  import Button from "$lib/components/base/button.svelte";
  import ButtonToggleMode from "./button-toggle-mode.svelte";
  import Design_001 from "$lib/components/tiles/design-001.svelte";
  import IconGithub from "$lib/components/icons/icon-github.svelte";
  import IconRightArrow from "$lib/components/icons/icon-right-arrow.svelte";
  import Link from "$lib/components/base/link.svelte";
  import Text from "$lib/components/base/text.svelte";
  import Title from "$lib/components/base/title.svelte";
  import { fade, slide } from "svelte/transition";
  import { onMount } from "svelte";
  import { twMerge } from "tailwind-merge";

  let animate = $state(false);
  let openAppShell = $state(false);

  function onAppShell() {
    openAppShell = true;
  }

  function offAppShell() {
    openAppShell = false;
  }

  onMount(() => {
    setTimeout(() => {
      animate = true;
    }, 1000);
  });
</script>

<div class="h-screen w-screen overflow-hidden">
  {#if !openAppShell}
    <div
      in:slide={{ axis: "x", duration: 300, delay: 500 }}
      out:slide={{ axis: "x", duration: 300, delay: 0 }}
    >
      <div
        class={twMerge(
          "p-2 sm:p-4 md:p-8 lg:p-16 w-screen h-screen grid place-self-center opacity-0 duration-500",
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
                "relative h-0 transition-all opacity-0 delay-1500 duration-500",
                animate && "opacity-100 h-full"
              )}
            >
              <div class="absolute hidden xl:block top-0 right-0 pr-4 pt-2">
                <p
                  class="text-sm absolute top-4 pl-2 pr-8 border-b -right-22 rotate-90 w-max"
                >
                  Sample Components
                </p>
                <div class="flex justify-end gap-4 mb-4">
                  <Button>Button</Button>
                </div>
                <div class="flex justify-end gap-4 mb-4">
                  <Button>Button</Button>
                  <Button>Button</Button>
                </div>
                <div class="flex justify-end gap-4 mb-4">
                  <Button>Button</Button>
                  <Button>Button</Button>
                  <Button>Button</Button>
                </div>
                <div class="flex justify-end gap-4">
                  <Button>Button</Button>
                  <Button>Button</Button>
                  <Button>Button</Button>
                  <Button>Button</Button>
                </div>
              </div>

              <Title class="font-bold text-3xl">Cliemtor Fabros</Title>
              <Text class="text-base-500">Hey! I’m a Frontend Developer.</Text>

              <div class="flex gap-2 mt-4">
                <Button
                  onclick={onAppShell}
                  class="gap-2 bg-gradient-to-r from-fg via-primary-950 to-primary-900 text-base-50 dark:from-bg"
                >
                  Know more about me <IconRightArrow />
                </Button>
              </div>
            </div>

            <div
              class={twMerge(
                "w-0 flex flex-col justify-end self-end transition-all duration-500 delay-1800 opacity-0",
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
    </div>
  {:else}
    <div
      in:fade={{ duration: 300, delay: 500 }}
      out:fade={{ duration: 300, delay: 0 }}
    >
      <div
        class={twMerge(
          "w-0 border-b h-min delay-1000 transition-all opacity-0 duration-500",
          animate && "w-full opacity-100"
        )}
      >
        <div class="container py-2 mx-auto flex justify-between items-center">
          <Link class="flex items-center pt-1 text-fg">
            <IconGithub class="inline text-primary" />
            <Text class="text-border font-mono">{`/`}</Text>
            <Text>clios</Text>
          </Link>
          <!-- BUTTON TOGGLE MODE -->
          <ButtonToggleMode />
        </div>
      </div>
    </div>
  {/if}
</div>
