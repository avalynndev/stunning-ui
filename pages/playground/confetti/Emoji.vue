<template>
  <main class="w-screen h-screen flex justify-center items-center">
    <Button @click="handleClick">Emoji</Button>
  </main>
</template>

<script lang="ts" setup>
import { useConfetti } from '~/composables/useConfetti'

const { confetti } = useConfetti()

const handleClick = () => {
  const scalar = 2
  const unicorn = confetti.shapeFromText({ text: '🦄', scalar })

  const defaults = {
    spread: 360,
    ticks: 60,
    gravity: 0,
    decay: 0.96,
    startVelocity: 20,
    shapes: [unicorn],
    scalar
  }

  function shoot() {
    confetti({
      ...defaults,
      particleCount: 30
    })

    confetti({
      ...defaults,
      particleCount: 5,
      flat: true
    })

    confetti({
      ...defaults,
      particleCount: 15,
      scalar: scalar / 2,
      shapes: ['circle']
    })
  }

  setTimeout(shoot, 0)
  setTimeout(shoot, 100)
  setTimeout(shoot, 200)
}
</script>

<style scoped></style>
