<!-- ChildComponent2.vue -->
<template>
  <div>
    <p>{{ sharedMessage }}</p>
  </div>
</template>

<script>
export default {
  name: "ChildComponent2",
  inject: ["sharedMessage"],
};
</script>

<style scoped>
p {
  font-size: 1.5rem;
}
</style>
