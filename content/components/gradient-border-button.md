---
navigation.title: Gradient Border Button
title: Gradient Border Button
description: Typically used to display dynamic text changes in the Hero Section.
category: button, cta
---

## Preview

<Playground url="/playground/gradient-border-button"></Playground>

## Installation

### Prerequisites

This component requires animation to be added in the `tailwind.config.ts` file for Tailwind CSS.

```ts
// tailwind.config.ts
module.exports = {
  theme: {
    extend: {
      backgroundImage: {
        'gradient-conic': 'conic-gradient(var(--tw-gradient-stops))'
      }
    }
  }
}
```

### Copy the source code

`/components/stunning/GradientBorderButton.vue`

<CollapseCodeWrapper>

```vue
<template>
  <Button
    variant="ghost"
    :class="
      cn(
        'group !relative inline-flex h-10 overflow-hidden rounded-xl p-[1px] ring-offset-black will-change-transform focus:outline-none focus:ring-1 focus:ring-offset-2'
      )
    "
  >
    <div
      :class="
        cn(
          'absolute inset-[-1000%] animate-spin [animation-duration:5s] blur bg-gradient-conic',
          gradientColor
        )
      "
    />
    <div
      :class="
        cn(
          'inline-flex h-full w-full cursor-pointer items-center justify-center rounded-xl px-8 py-1 text-sm font-medium',
          'bg-gradient-to-t from-neutral-50 dark:from-neutral-800 to-white dark:to-black text-neutral-950 dark:text-neutral-300 backdrop-blur-3xl',
          'dark:group-hover:from-neutral-700 dark:group-hover:to-neutral-950 group-hover:from-neutral-50 group-hover:to-white'
        )
      "
    >
      <span
        class="transition-transform duration-100 ease-in-out group-hover:scale-105"
      >
        <slot />
      </span>
    </div>
  </Button>
</template>

<script lang="ts" setup>
import { cn } from '~/lib/utils'
import { Button } from '@/components/ui/button'

withDefaults(defineProps<{ gradientColor?: string }>(), {
  gradientColor: 'from-sky-700 via-blue-500 to-emerald-400'
})
</script>

<style scoped></style>
```

</CollapseCodeWrapper>

## Usage

### Default

```vue
<template>
  <GradientBorderButton> Sign in </GradientBorderButton>
</template>
```

### Change Graident Color

```vue
<template>
  <GradientBorderButton gradientColor="from-sky-400 via-rose-400 to-lime-400">
    Sign in
  </GradientBorderButton>
</template>
```

## Props

| Prop          | Type   | Description                                           | Default                                    |
| :------------ | :----- | :---------------------------------------------------- | :----------------------------------------- |
| gradientColor | String | the background gradient class of the border animation | 'from-sky-700 via-blue-500 to-emerald-400' |

## Inspiration

-