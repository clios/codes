<script lang="ts">
  import type { HTMLAttributes } from "svelte/elements";
  import type { Snippet } from "svelte";
  import { twMerge } from "tailwind-merge";

  type Props = HTMLAttributes<HTMLElementTagNameMap["div"]> & {
    children?: Snippet;
    class?: string;
  };

  let { children, class: className, ...props }: Props = $props();
</script>

<div class={twMerge("relative p-4", className)} {...props}>
  <div
    class="top-0 right-0 absolute border-t-2 border-r-2 border-base-500 size-4"
  ></div>
  <div
    class="top-0 left-0 absolute border-t-2 border-base-500 border-l-2 size-4"
  ></div>
  <div
    class="right-0 bottom-0 absolute border-r-2 border-b-2 border-base-500 size-4"
  ></div>
  <div
    class="bottom-0 left-0 absolute border-b-2 border-base-500 border-l-2 size-4"
  ></div>
  {@render children?.()}
</div>
