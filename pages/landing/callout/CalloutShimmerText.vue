<template>
  <NuxtLayout name="playground">
    <main class="w-full h-full flex flex-col justify-center items-center px-8">
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
    </main>
  </NuxtLayout>
</template>

<script lang="ts" setup>
import ShimmerText from '@/components/stunning/ShimmerText.vue'
</script>

<style scoped></style>
