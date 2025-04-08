<script lang="ts">
  import type { HTMLAttributes } from "svelte/elements";
  import type { Snippet } from "svelte";
  import { twMerge } from "tailwind-merge";

  type Props = HTMLAttributes<HTMLElementTagNameMap["section"]> & {
    children?: Snippet;
    class?: string;
  };

  let { children, class: className, ...props }: Props = $props();
</script>

<div class={twMerge("w-full max-w-[20rem] sm:container", className)} {...props}>
  {@render children?.()}
</div>
