<script setup>
const menu = [
  {
    text: 'Vue.js',
    url: 'https://vuejs.org/',
  },
  {
    text: 'React',
    url: 'https://reactjs.org/',
  },
  {
    text: 'Angular',
    url: 'https://angular.io/',
  },
  {
    text: 'Svelte',
    url: 'https://svelte.dev/',
  },
]
</script>

<template>
  <nav class="main-navigation">
    <ul>
      <li v-for="menuItem in menu" :key="menuItem.url">
        <a :href="menuItem.url">{{ menuItem.text }}</a>
      </li>
    </ul>
  </nav>
</template>

<style scoped>

</style>
