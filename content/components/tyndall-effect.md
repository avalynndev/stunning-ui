---
navigation.title: Tyndall Effect
title: Tyndall Effect
description: Tyndall effect is light scattering by particles, used in the hero as a background
category: background, hero
---

::code-group

::div{label="Preview"}
<Playground url="/playground/tyndall-effect" ></Playground>
::

```vue [Code]
<template>
  <main class="w-full h-full bg-black">
    <TyndallEffect>
      <div
        class="absolute top-48 left-1/2 -translate-x-1/2 transform w-full flex flex-col items-center px-5"
      >
        <p
          class="rounded-full border border-white/50 px-4 py-1 text-xs font-bold uppercase tracking-widest text-white opacity-50"
        >
          New Version 1.0
        </p>

        <h1
          class="mt-8 bg-gradient-to-br from-sky-200/90 via-sky-50 to-white bg-clip-text text-center text-4xl font-medium tracking-tight text-transparent md:text-6xl"
        >
          Stunning UI is a better way <br />
          to build websites
        </h1>
      </div>
      <template #particles>
        <ParticlesEffect
          :density="256"
          class="absolute inset-x-0 bottom-0 h-full w-full [mask-image:radial-gradient(50%_50%,white,transparent_85%)] z-10"
        />
      </template>
    </TyndallEffect>
  </main>
</template>

<script lang="ts" setup>
import TyndallEffect from '@/components/stunning/TyndallEffect.vue'
import ParticlesEffect from '@/components/stunning/ParticlesEffect.vue'
</script>

<style scoped></style>
```

::

## Installation

::MSteps

### Prerequisites

This component requires the package [@vueuse/motion](https://motion.vueuse.org/).

```bash
pnpm i @vueuse/motion
# or
bun i @vueuse/motion
```

### Copy the source code

`/components/stunning/TyndallEffect.vue`

::CodeCollapse

```vue
<template>
  <div
    class="sui-tyndall-effect relative flex gap-10 min-h-screen overflow-hidden h-auto w-full justify-start items-center"
  >
    <div
      class="streak"
      v-motion
      :initial="{ opacity: 0, rotate: '64deg', scale: 0.5 }"
      :enter="{ opacity: 0.8, rotate: '64deg', scale: 1 }"
      :duration="2000"
    />
    <div
      class="streak"
      v-motion
      :initial="{ opacity: 0, rotate: '48deg', scale: 0.5 }"
      :enter="{ opacity: 0.24, rotate: '48deg', scale: 1 }"
      :duration="2000"
    />
    <div
      class="streak"
      v-motion
      :initial="{ opacity: 0, rotate: '36deg', scale: 0.5 }"
      :enter="{ opacity: 0.64, rotate: '36deg', scale: 1 }"
      :duration="2000"
    />
    <div class="overlay"></div>
    <div class="particles-effect" v-if="$slots.particles">
      <slot name="particles" />
    </div>
    <slot />
  </div>
</template>

<script lang="ts" setup></script>

<style scoped>
.sui-tyndall-effect {
  --sui-tyndall-effect-bg-first-color: #00b7fa;
  --sui-tyndall-effect-bg-second-color: rgb(0, 40, 128);
  --sui-tyndall-effect-bg-third-color: rgba(0, 53, 97, 0.71);
  --sui-tyndall-effect-bg-fourth-color: rgb(0, 0, 0);
  --sui-tyndall-effect-streak-color: #00e1ff;
  background: radial-gradient(
    102% 64% at 1% 48%,
    var(--sui-tyndall-effect-bg-first-color) 0%,
    var(--sui-tyndall-effect-bg-second-color) 54%,
    var(--sui-tyndall-effect-bg-third-color) 72%,
    var(--sui-tyndall-effect-bg-fourth-color) 100%
  );
  width: 105%;
}

.sui-tyndall-effect .overlay {
  background: linear-gradient(
    180deg,
    #000000 0%,
    rgba(0, 0, 0, 0.32) 43%,
    rgba(0, 0, 0, 0.13) 70%,
    rgba(0, 0, 0, 0) 100%
  );
  flex: none;
  height: 226px;
  left: 0;
  overflow: hidden;
  pointer-events: none;
  position: absolute;
  right: 0;
  top: 0;
  z-index: 11;
}

.sui-tyndall-effect .streak {
  background: linear-gradient(
    90deg,
    var(--sui-tyndall-effect-streak-color) 16%,
    rgba(255, 255, 255, 0) 100%
  );
  flex: none;

  mask: linear-gradient(
    180deg,
    rgba(0, 0, 0, 0) 0%,
    rgba(0, 0, 0, 0.5) 35%,
    rgba(0, 0, 0, 0.50052) 64%,
    rgba(0, 0, 0, 0) 100%
  );
  mix-blend-mode: overlay;
  overflow: hidden;
  pointer-events: none;
  position: absolute;
  width: 141%;
}

.sui-tyndall-effect .streak:nth-child(1) {
  height: 180px;
  left: -416px;
  top: 256px;
  opacity: 0.8;
}
.sui-tyndall-effect .streak:nth-child(2) {
  opacity: 0.24;
  height: 120px;
  left: -164px;
  top: 440px;
}
.sui-tyndall-effect .streak:nth-child(3) {
  height: 160px;
  left: -200px;
  top: 200px;
}

.sui-tyndall-effect .particles-effect {
  flex: none;
  height: 100vh;
  left: 0;
  mask: linear-gradient(
    225deg,
    rgba(0, 0, 0, 0) 30%,
    rgb(0, 0, 0) 36%,
    rgb(0, 0, 0) 63%,
    rgba(0, 0, 0, 0) 76%
  );
  position: absolute;
  right: 0;
  top: 0;
}
</style>
```

::

::

## Example

### Colors

::code-group

::div{label="Preview"}
<Playground url="/playground/tyndall-effect/WithTheme" ></Playground>
::

```vue [Code]
<template>
  <main class="w-full h-full bg-black">
    <TyndallEffect
      :style="{
        '--sui-tyndall-effect-bg-first-color': '#10b981',
        '--sui-tyndall-effect-bg-second-color': '#065f46',
        '--sui-tyndall-effect-bg-third-color': 'rgb(12, 95, 70, .80)',
        '--sui-tyndall-effect-bg-fourth-color': 'rgb(0, 0, 0)',
        '--sui-tyndall-effect-streak-color': '#a5f3fc'
      }"
    >
      <div
        class="absolute top-48 left-1/2 -translate-x-1/2 transform w-full flex flex-col items-center px-5"
      >
        <p
          class="rounded-full border border-white/50 px-4 py-1 text-xs font-bold uppercase tracking-widest text-white opacity-50"
        >
          New Version 1.0
        </p>

        <h1
          class="mt-8 bg-gradient-to-br from-teal-200/90 via-teal-50 to-white bg-clip-text text-center text-4xl font-medium tracking-tight text-transparent md:text-6xl"
        >
          Stunning UI is a better way <br />
          to build websites
        </h1>
      </div>
      <template #particles>
        <ParticlesEffect
          :density="256"
          class="absolute inset-x-0 bottom-0 h-full w-full [mask-image:radial-gradient(50%_50%,white,transparent_85%)] z-10"
        />
      </template>
    </TyndallEffect>
  </main>
</template>

<script lang="ts" setup>
import TyndallEffect from '@/components/stunning/TyndallEffect.vue'
import ParticlesEffect from '@/components/stunning/ParticlesEffect.vue'
</script>

<style scoped></style>
```

::

## Props

| Prop  | Type   | Description            | Default |
| :---- | :----- | :--------------------- | :------ |
| color | String | the color of the light | ""      |

## Inspiration

- [https://www.framer.com/](https://www.framer.com/)