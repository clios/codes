<script lang="ts">
  import type { SVGAttributes } from "svelte/elements";
  import type { Snippet } from "svelte";
  import { twMerge } from "tailwind-merge";

  type Props = SVGAttributes<SVGSVGElement> & {
    children?: Snippet;
    class?: string;
  };

  let { children, class: className, ...props }: Props = $props();
</script>

<!-- Note: update proper viewBox value -->
<svg
  xmlns="http://www.w3.org/2000/svg"
  class={twMerge("max-w-6 min-w-6", className)}
  viewBox="0 0 24 24"
  {...props}
>
  <path
    fill="none"
    stroke="currentColor"
    stroke-linecap="round"
    stroke-linejoin="round"
    stroke-width="2"
    d="M4 6h16M7 12h13m-10 6h10"
  />
</svg>
