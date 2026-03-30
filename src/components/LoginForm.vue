<template>
  <v-container class="h-full flex items-center justify-center">
    <v-card class="pa-6 w-full max-w-sm" elevation="8" rounded="xl">
      <v-card-title class="text-center text-2xl font-bold mb-4">
        Welcome Back
      </v-card-title>
      <v-card-text>
        <v-form @submit.prevent="handleLogin">
          <v-text-field
            v-model="email"
            label="Email"
            type="email"
            variant="outlined"
            prepend-inner-icon="mdi-email-outline"
            class="mb-2"
            required
          ></v-text-field>

          <v-text-field
            v-model="password"
            :append-inner-icon="showPassword ? 'mdi-eye-off-outline' : 'mdi-eye-outline'"
            :type="showPassword ? 'text' : 'password'"
            label="Password"
            variant="outlined"
            prepend-inner-icon="mdi-lock-outline"
            class="mb-4"
            required
            @click:append-inner="showPassword = !showPassword"
          ></v-text-field>

          <v-btn type="submit" color="primary" size="large" block class="mt-2 text-none">
            Sign In
          </v-btn>
        </v-form>
      </v-card-text>
    </v-card>
  </v-container>
</template>

<script setup lang="ts">
import { ref } from 'vue'

const email = ref('')
const password = ref('')
const showPassword = ref(false)

const handleLogin = () => {
  console.log('Mencoba login dengan:', email.value, password.value)
  alert(`Login dipicu!\nEmail: ${email.value}`)
}
</script>
