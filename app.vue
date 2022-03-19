<script setup lang="ts">
import TheHeader from './components/TheHeader.vue';
</script>

<template>
  <div class="h-screen flex flex-col">
    <TheHeader></TheHeader>
    <div class="flex h-full z-0">
      <TheSidemenu></TheSidemenu>
      <canvas class="bg-gray-200 w-full"></canvas>
    </div>
  </div>
</template>
