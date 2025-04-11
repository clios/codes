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
  class={twMerge("min-w-6 max-w-6", className)}
  viewBox="0 0 199 68"
  {...props}
>
  <path d="M197 34L131 1V67L197 34Z" fill="currentColor" />
  <path
    d="M0 34L131 34M131 1L197 34L131 67V1Z"
    stroke-width="10"
    stroke="currentColor"
    fill="currentColor"
  />
</svg>
