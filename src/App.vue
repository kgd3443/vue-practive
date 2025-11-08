<template>
  <e12-ref-component />
</template>

<script lang="ts">
import { defineComponent } from 'vue';
import E08CompositionApi from "@/components/example5/E-08-composition-api.vue";
import E09CompositionApi from "@/components/example5/E-09-composition-API2.vue";
import E10Ref from "@/components/example6/E-10-ref.vue";
import E11Reactive from "@/components/example6/E-11-reactive.vue";
import E12RefComponent from "@/components/example6/E-12-ref-component.vue";
import E07OptionsApi from "@/components/example5/E-07-Options-API.vue";




export default defineComponent({
  name: 'App',
  components: {
    E12RefComponent
  }
});
</script>

<style>
</style>
