<script lang="ts">
  import type { HTMLButtonAttributes } from "svelte/elements";
  import type { Snippet } from "svelte";
  import { twMerge } from "tailwind-merge";

  type Variant =
    | "default"
    | "inverted"
    | "primary"
    | "secondary"
    | "destructive"
    | "outline"
    | "ghost";

  type Props = HTMLButtonAttributes & {
    children?: Snippet;
    class?: string | null;
    disabled?: boolean;
    edge?: "default" | "circle" | "sharp";
    loading?: boolean;
    size?: "default" | "icon" | "small" | "fit";
    variant?: Variant;
  };

  let {
    children,
    class: className,
    disabled = false,
    edge = "default",
    loading = $bindable(false),
    size = "default",
    variant = "default",
    ...props
  }: Props = $props();
</script>

<button
  class={twMerge(
    "h-min w-max", // size
    "hover:z-1 relative flex items-center gap-1", // layout and positioning
    "ring ring-primary ring-offset-bg focus:ring-2", // ring
    "cursor-pointer transition-all", // visual

    // VARIANT: DEFAULT
    variant === "default" && [
      "text-bg bg-fg", // text and background
      "hover:ring-offset-2 focus:ring-offset-2", // hover and focus
      "active:ring-offset-0 active:ring-2", // active
    ],

    // VARIANT: INVERTED
    variant === "inverted" && [
      "text-fg bg-bg", // text and background
      "hover:ring-offset-2 focus:ring-offset-2", // hover and focus
      "active:ring-offset-0 active:ring-2", // active
    ],

    variant === "primary" && "bg-primary text-primary-fg border-primary",
    variant === "secondary" &&
      "bg-secondary text-secondary-fg border-secondary",
    variant === "destructive" &&
      "bg-destructive text-destructive-fg border-destructive outline-destructive",
    variant === "outline" && "text-fg border-fg bg-none",

    // VARIANT: GHOST
    variant === "ghost" && [
      "text-fg bg-none", // text and background
      "focus:text-primary focus:outline-none focus:ring-0", // focus
      "hover:text-primary active:text-fg", // hover and active
      "ring-0", // ring
    ],

    // SIZES
    size === "default" && "px-3 py-1 text-base",
    size === "icon" && "p-1",
    size === "small" && "h-6 px-2 text-sm leading-6",
    size === "fit" && "p-0",

    // EDGES
    edge === "default" && "rounded",
    edge === "circle" && "rounded-full",
    edge === "sharp" && "rounded-none",

    // LOADING
    loading &&
      "border-disabled text-disabled bg-disabled cursor-not-allowed outline-none",

    // DISABLED
    disabled &&
      "border-disabled text-disabled-fg bg-disabled cursor-not-allowed outline-none",

    className
  )}
  disabled={loading || disabled}
  {...props}
>
  {#if loading}
    {@render IconSpinner()}
  {/if}
  {@render children?.()}
</button>

{#snippet IconSpinner()}
  <svg
    xmlns="http://www.w3.org/2000/svg"
    class="right-1/2 bottom-1/2 absolute size-4 text-primary translate-x-1/2 translate-y-1/2 animate-spin"
    viewBox="0 0 16 16"
  >
    <path
      fill="currentColor"
      d={`M8 0A8 8 0 0 0 .002 7.812C.094 4.033 2.968 1 6.5 1C10.09 1 13 4.134 13 8a1.5 1.5 ` +
        `0 0 0 3 0a8 8 0 0 0-8-8m0 16a8 8 0 0 0 7.998-7.812C15.906 11.967 13.032 15 9.5 ` +
        `15C5.91 15 3 11.866 3 8a1.5 1.5 0 0 0-3 0a8 8 0 0 0 8 8`}
    />
  </svg>
{/snippet}
