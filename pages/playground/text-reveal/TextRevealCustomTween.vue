<template>
  <main class="w-screen px-24 py-12 h-[300vh]">
    <div
      className="w-full h-screen pb-16 flex flex-col items-center justify-between"
    >
      <span class="text-neon-wb text-2xl text-white/30">
        Scroll-driven Text Reveal
      </span>
      <Button
        size="icon"
        class="rounded-full animate-bounce"
        @click="handleScroll"
      >
        <Icon name="ri:arrow-down-line" />
      </Button>
    </div>
    <TextReveal
      :text="paragraphPlaceholder"
      textClass="font-semibold"
      splitting-by="chars"
      :fromVars="{
        translateY: '10px',
        scaleY: 1.5,
        willChange: 'filter, transform',
        color: 'transparent'
      }"
      :toVars="{
        translateY: '0px',
        scaleY: 1,
        stagger: 0.04,
        ease: 'sine',
        color: '#4fa'
      }"
    />
    <div class="h-screen w-full"></div>
  </main>
</template>

<script lang="ts" setup>
import TextReveal from '@/components/stunning/TextReveal.vue'
import { paragraphPlaceholder } from '~/lib/constants'
import { useSmoothScroll } from '@/composables/useSmoothScroll'

const text =
  'Stunning UI is Designed for Developers、Designers、Creators、Indie Hackers'

useSmoothScroll()

const handleScroll = () => {
  window.scrollTo({ top: document.body.scrollHeight / 3, behavior: 'smooth' })
}
</script>

<style scoped></style>
