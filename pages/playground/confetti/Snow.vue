<template>
  <main class="w-screen h-screen flex justify-center items-center">
    <Button @click="handleClick">Snow</Button>
  </main>
</template>

<script lang="ts" setup>
import { useConfetti } from '~/composables/useConfetti'

const { confetti } = useConfetti()

const handleClick = () => {
  const duration = 15 * 1000
  const animationEnd = Date.now() + duration
  let skew = 1

  function randomInRange(min: number, max: number) {
    return Math.random() * (max - min) + min
  }

  ;(function frame() {
    const timeLeft = animationEnd - Date.now()
    const ticks = Math.max(200, 500 * (timeLeft / duration))
    skew = Math.max(0.8, skew - 0.001)

    confetti({
      particleCount: 1,
      startVelocity: 0,
      ticks: ticks,
      origin: {
        x: Math.random(),
        // since particles fall down, skew start toward the top
        y: Math.random() * skew - 0.2
      },
      colors: ['#ffffff'],
      shapes: ['circle'],
      gravity: randomInRange(0.4, 0.6),
      scalar: randomInRange(0.4, 1),
      drift: randomInRange(-0.4, 0.4)
    })

    if (timeLeft > 0) {
      requestAnimationFrame(frame)
    }
  })()
}
</script>

<style scoped></style>
