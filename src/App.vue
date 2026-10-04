<script setup>
import DataFilter from './components/DataFilter.vue'
import MainNavigation from './components/MainNavigation.vue'
import UserForm from './components/UserForm.vue'
</script>

<template>
  <MainNavigation />

  <main>
    <section>
      <h1>DataFilter</h1>
      <DataFilter />
    </section>

    <section>
      <h1>UserForm</h1>
      <UserForm />
    </section>
  </main>
</template>
