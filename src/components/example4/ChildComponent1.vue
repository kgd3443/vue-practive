<!-- ChildComponent1.vue -->
<template>
  <div>
    <p>{{ message }}</p>
    <button @click="emit('custom-event', 'Hello from child 1')">Emit Event</button>
  </div>
</template>

<script setup>
const props = defineProps({
  message: {
    type: String,
    required: true,
  },
})
const emit = defineEmits(['custom-event'])
</script>

<style scoped>
p {
  color: red;
}
</style>
