<template>
  <main class="w-full h-full container">
    <div
      class="relative pt-24 sm:pt-32 max-w-screen-xl flex flex-col justify-center items-center px-8 gap-8"
    >
      <div
        class="group rounded-full border border-black/5 bg-neutral-100 text-base text-white transition-all ease-in hover:cursor-pointer hover:bg-neutral-200 dark:border-white/5 dark:bg-neutral-900 dark:hover:bg-neutral-800"
      >
        <ShimmerText
          class="inline-flex items-center justify-center px-4 py-1 transition ease-out hover:text-neutral-600 hover:duration-300 hover:dark:text-neutral-400"
        >
          ✨ Stunning UI 1.0 Beta
          <Icon
            name="ri:arrow-right-line"
            class="w-4 h-4 ml-1 size-3 transition-transform duration-300 ease-in-out group-hover:translate-x-0.5"
          />
        </ShimmerText>
      </div>
      <h1
        class="text-5xl text-center font-bold tracking-tight sm:text-6xl text-transparent bg-clip-text bg-gradient-to-b from-neutral-950 to-neutral-500 dark:from-white dark:to-neutral-700 to-92%"
      >
        Create Stunning Websites
        <br />
        That Stand Out
      </h1>
      <div class="text-lg tracking-tight text-center text-muted-foreground">
        Stunning UI is a collection of interactive Tailwind CSS components built
        for Vue and Nuxt.
      </div>
      <div class="flex flex-wrap gap-x-6 gap-y-3 justify-center">
        <Button variant="brand" @click="navigateTo('/components')">
          Browse Components
        </Button>
        <Button variant="outline" class="group">
          Getting Started
          <Icon
            name="ri:arrow-right-line"
            class="w-4 h-4 ml-1 size-3 transition-transform duration-300 ease-in-out group-hover:translate-x-0.5"
          />
        </Button>
      </div>
      <GridPattern
        :width="60"
        :height="60"
        :x="-1"
        :y="-1"
        class="[mask-image:radial-gradient(100%_100%_at_top_center,white,transparent)]"
      />
    </div>
    <div class="py-24 sm:py-32 max-w-screen-xl">
      <div
        class="relative mx-auto px-4 sm:px-6 lg:px-8 max-w-screen-xl gap-16 sm:gap-y-24 flex flex-col"
      >
        <div
          class="bg-neutral-900/5 dark:bg-white/5 ring-1 ring-inset ring-neutral-900/10 dark:ring-white/10 rounded-xl lg:-m-4 p-4 z-10"
        >
          <div
            class="aspect-video rounded-lg relative overflow-hidden border border-dashed border-neutral-900/10 dark:border-white/10"
          >
            <ImagePlaceholder />
          </div>
        </div>
      </div>
    </div>
  </main>
</template>

<script lang="ts" setup>
import ShimmerText from '@/components/stunning/ShimmerText.vue'
import GridPattern from '@/components/stunning/GridPattern.vue'
import ImagePlaceholder from '@/components/ImagePlaceholder.vue'
</script>

<style scoped></style>
