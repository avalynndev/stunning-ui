<template>
  <svg
    class="absolute inset-0 h-full w-full stroke-neutral-900/10 dark:stroke-white/10"
    fill="none"
  >
    <defs>
      <pattern
        id="pattern-image-placeholder"
        x="0"
        y="0"
        width="10"
        height="10"
        patternUnits="userSpaceOnUse"
      >
        <path d="M-3 13 15-5M-5 5l18-18M-1 21 17 3"></path>
      </pattern>
    </defs>
    <rect
      stroke="none"
      fill="url(#pattern-image-placeholder)"
      width="100%"
      height="100%"
    ></rect>
  </svg>
</template>
