<!-- ParentComponent.vue -->
<template>
  <div>
    <ChildComponent1
        :message="parentMessage"
        @custom-event="handleEvent"
    />
    <!--ChildComponent2:
    <ChildComponent2
      :message="parentMessage"
      @custom-event="handleEvent"
    />
    -->
  </div>
</template>

<script setup>
import { ref } from 'vue'
import ChildComponent1 from './ChildComponent1.vue'
import ChildComponent2 from './ChildComponent2.vue' // 필요 시 사용

const parentMessage = ref('Hello from parent')

function handleEvent(payload) {
  console.log(payload)
}
</script>
