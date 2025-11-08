<!-- ChildComponent.vue -->
<template>
  <div>
    <p>{{ message }}</p>
    <button @click="emit('custom-event', 'Hello from child')">
      Emit Event
    </button>
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
