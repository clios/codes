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
  class={twMerge("min-w-3 max-w-3", className)}
  viewBox="0 0 44 63"
  {...props}
>
  <path
    d="M39.5 0L0 62.5H4L43.5 0H39.5Z"
    fill="currentColor"
    stroke-width="2"
  />
</svg>
