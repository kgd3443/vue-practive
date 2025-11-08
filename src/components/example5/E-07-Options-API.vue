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

<script lang="ts">
import { defineComponent } from 'vue'

export default defineComponent({
  name: 'E07OptionsApi',
  data() {
    return {
      title: 'User Information',
      firstName: 'John',
      lastName: 'Doe',
      greetCount: 0,
      message: ''
    }
  },
  computed: {
    fullName(): string {
      return `${this.firstName} ${this.lastName}`.trim()
    }
  },
  methods: {
    greet() {
      this.greetCount++
      this.message = `Hello, ${this.fullName || 'Anonymous'}!`
    }
  },
  beforeUnmount() {
    // cleanup 필요 시
  }
})
</script>
