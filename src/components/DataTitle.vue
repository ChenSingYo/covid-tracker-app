<template>
  <div class="text-center">
    <h2 class="text-3xl font-bold">{{ text }}</h2>
    <div class="text-2xl mt-4 mb-10">
      {{ timestamp }}
    </div>
  </div>
</template>

<script setup>
import dayjs from 'dayjs'
import { computed, defineProps } from 'vue'

const props = defineProps({
  text: {
    type: String,
    require: true
  },
  dataDate: {
    type: String,
    require: true
  }
})

const timestamp = computed(() => dayjs(props.dataDate).format('MMMM D YYYY, h:mm:ss a'))

</script>

<style>

</style>
