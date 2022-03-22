<script setup lang="ts">
import TheHeader from './components/TheHeader.vue';

const useCanvas = (canvas) => {
  canvas.value.width = 1024
  canvas.value.height = 1024
  const ctx = canvas.value.getContext('2d')
  ctx.fillRect(0, 0, 1024, 1024)

  return { canvas }
}

const bufferCanvas = ref<HTMLCanvasElement>()
const mainCanvas = ref<HTMLCanvasElement>()

let canvas

onMounted(() => {
  const c = useCanvas(bufferCanvas) 
  canvas = ref(c.canvas)
  const ctx = mainCanvas.value.getContext('2d')
  // console.log(ctx)
  ctx.drawImage(canvas.value, 10, 10, 100, 100)
})
</script>

<template>
  <div class="h-screen flex flex-col">
    <TheHeader></TheHeader>
    <div class="flex h-full z-0">
      <TheSidemenu></TheSidemenu>
      <canvas class="hidden" ref="bufferCanvas"></canvas>
      <canvas class="bg-gray-200 w-full" ref="mainCanvas"></canvas>
    </div>
  </div>
</template>
