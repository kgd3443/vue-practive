<template>
  <div>
    <h2>{{ title }}</h2>
    <p>Full Name: {{ fullName }}</p>

    <input v-model="firstName" placeholder="First Name" />
    <input v-model="lastName" placeholder="Last Name" />

    <button @click="greet">Greet</button>
    <p>Greeting Count: {{ greetCount }}</p>
    <p>{{ message }}</p>
  </div>
</template>

<script setup lang="ts">
import { ref, computed } from 'vue'

const title = ref('User Information')
const firstName = ref('John')
const lastName  = ref('Doe')
const greetCount = ref(0)
const message = ref('')

const fullName = computed(() => `${firstName.value} ${lastName.value}`.trim())

function greet() {
  greetCount.value++
  message.value = `Hello, ${fullName.value || 'Anonymous'}!`
}
</script>

<script lang="ts">
export default { name: 'E08CompositionApi' }
</script>
