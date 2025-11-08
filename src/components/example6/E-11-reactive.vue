<template>
  <div>
    <p>Name: {{ person.name }}</p>
    <p>Age: {{ person.age }}</p>
    <button @click="incrementAge">Increment Age</button>
  </div>
</template>

<script setup lang="ts">
import { reactive } from 'vue'

const person = reactive({
  name: 'John Doe',
  age: 30,
})

function incrementAge() {
  person.age++
}
</script>

<script lang="ts">
export default { name: 'E11Reactive' }
</script>
