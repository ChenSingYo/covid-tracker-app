<template>
<div class="grid md:grid-cols-2 gap-4">
  <!-- box1 -->
  <div class="shadow-md bg-blue-100 p-10 text-center rounded">
    <h3 class="text-3xl text-blue-900 font-bold mb-4">Cases</h3>
    <div class="text-2xl mb-4">
      <span class="font-bold">New:</span>
      {{ numberWithCommas(stats.NewConfirmed) }}
    </div>
    <div class="text-2xl mb-4">
      <span class="font-bold">Total:</span>
      {{ numberWithCommas(stats.TotalConfirmed) }}
    </div>
  </div>
  <!-- box2 -->
  <div class="shadow-md bg-blue-200 p-10 text-center rounded">
    <h3 class="text-3xl text-blue-900 font-bold mb-4">Deaths</h3>
    <div class="text-2xl mb-4">
      <span class="font-bold">New:</span>
      {{ numberWithCommas(stats.NewDeaths) }}
    </div>
    <div class="text-2xl mb-4">
      <span class="font-bold">Total:</span>
      {{ numberWithCommas(stats.TotalDeaths) }}
    </div>
  </div>
</div>
</template>

<script setup>
import { defineProps } from 'vue'

const props = defineProps({
  stats: {
    type: Object,
    require: true
  }
})

function numberWithCommas (x) {
  return x.toString()
    .replace(/\B(?=(\d{3})+(?!\d))/g, ',')
}

numberWithCommas(props)

</script>

<style>

</style>
