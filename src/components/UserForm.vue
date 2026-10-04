<script setup>
import { computed, ref } from 'vue'

const username = ref('')
const password = ref('')
const confirmPassword = ref('')

const usernameHasError = computed(
  () => username.value.length < 5 || username.value === password.value,
)

const passwordHasError = computed(
  () => password.value.length < 8 || password.value === username.value,
)

const confirmPasswordHasError = computed(
  () =>
    confirmPassword.value.length < 8 ||
    confirmPassword.value !== password.value,
)

function submitForm() {
  if (
    usernameHasError.value ||
    passwordHasError.value ||
    confirmPasswordHasError.value
  ) {
    return
  }

  window.alert(
    `Username: ${username.value}\nPassword: ${password.value}\nConfirm password: ${confirmPassword.value}`,
  )

  username.value = ''
  password.value = ''
  confirmPassword.value = ''
}
</script>

<template>
  <form novalidate @submit.prevent="submitForm">
    <div>
      <label for="username">Username</label>
      <input id="username" v-model="username" type="text" />
      <p v-if="usernameHasError" class="error-message">
        Username must be at least 5 characters long and different from password
      </p>
    </div>

    <div>
      <label for="password">Password</label>
      <input id="password" v-model="password" type="password" />
      <p v-if="passwordHasError" class="error-message">
        Password must be at least 8 characters long and different from username
      </p>
    </div>

    <div>
      <label for="confirmPassword">Confirm password</label>
      <input
        id="confirmPassword"
        v-model="confirmPassword"
        type="password"
      />
      <p v-if="confirmPasswordHasError" class="error-message">
        Confirm password must be at least 8 characters long and match with
        password
      </p>
    </div>

    <button type="submit">Küldés</button>
  </form>
</template>

<style scoped>

</style>
