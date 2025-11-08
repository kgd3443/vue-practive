<template>
  <div>
    <h2>{{ title }}</h2>

    <p>Full Name: {{ fullName }}</p>
    <input v-model="firstName" placeholder="First Name" />
    <input v-model="lastName"  placeholder="Last Name" />

    <button @click="onGreetClick">Greet</button>
    <p>Greeting Count: {{ greetCount }}</p>
    <p>{{ message }}</p>
  </div>
</template>

<script lang="ts">
import { defineComponent, ref, computed } from 'vue'

export default defineComponent({
  name: 'E09CompositionApi',
  props: {
    // 🔄 title → initialTitle 로 변경
    initialTitle: { type: String, required: false, default: 'User Information' },
  },
  emits: ['greeted'],
  setup(props, { emit }) {
    const title = ref(props.initialTitle)
    const firstName = ref('John')
    const lastName  = ref('Doe')
    const greetCount = ref(0)
    const message = ref('')

    const fullName = computed(() => `${firstName.value} ${lastName.value}`.trim())

    function onGreetClick() {
      greetCount.value++
      const name = fullName.value || 'Anonymous'
      message.value = `Hello, ${name}!`
      emit('greeted', { name, count: greetCount.value })
    }

    return { title, firstName, lastName, greetCount, message, fullName, onGreetClick }
  },
})
</script>
