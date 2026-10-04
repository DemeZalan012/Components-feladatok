<script setup>
import { computed, ref, watch } from 'vue'

const data = [
  { id: 1, name: 'Kai Cenat' },
  { id: 2, name: 'Jason' },
  { id: 3, name: 'MC Isti' },
  { id: 4, name: 'Busak Jozsef' },
]

const searchTerm = ref('')

const filteredData = computed(() => {
  const normalizedSearchTerm = searchTerm.value.toLowerCase()

  return data.filter((person) =>
    person.name.toLowerCase().includes(normalizedSearchTerm),
  )
})

watch(searchTerm, (newValue) => {
  console.log(newValue)
})
</script>

<template>
  <div>
    <label for="search">Keresés:</label>
    <input id="search" v-model="searchTerm" type="text" />

    <ul>
      <li v-for="person in filteredData" :key="person.id">
        {{ person.name }}
      </li>
    </ul>
  </div>
</template>
