<script lang="ts">
  import type { HTMLAnchorAttributes } from "svelte/elements";
  import type { Snippet } from "svelte";
  import { twMerge } from "tailwind-merge";

  type Props = {
    children?: Snippet;
    class?: string;
  } & HTMLAnchorAttributes;

  let { children, class: className, ...props }: Props = $props();
</script>

<a
  class={twMerge(
    "group relative rounded w-fit cursor-pointer", // base
    "hover:text-primary", // hovering
    "active:outline-2 active:outline-offset-0", // active
    className,
  )}
  {...props}
>
  {@render children?.()}
</a>
