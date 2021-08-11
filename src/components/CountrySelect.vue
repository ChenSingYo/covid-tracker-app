<template>
  <select @change="onChange"
    v-model="selected"
    class="form-select mt-10 block w-full border p-3 rounded"
  >
    <option value="0">Select Country</option>
    <option v-for="country in countries" :value="country.ID" :key="country.ID">
      {{ country.Country}}
    </option>
  </select>
</template>

<script setup>
import { ref, defineProps, defineEmits } from 'vue'

const props = defineProps({
  countries: {
    type: Object,
    require: true
  }
})

const selected = ref(0)

const emit = defineEmits(['get-country'])

function onChange () {
  const country = props.countries.find((item) => item.ID === selected.value)
  emit('get-country', country)
}

</script>

<style>

</style>
