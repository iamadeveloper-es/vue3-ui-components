<script lang="ts">
export default {
  name: 'app-spinner'
};
</script>
<script setup lang="ts">

defineProps({
  show: {
    type: Boolean,
    default: true
  }
});
</script>

<template lang="pug">
.app-spinner(v-if="show") 
    svg.spinner(viewBox="0 0 50 50")
        circle.path(cx="25", cy="25", r="20", fill="none", stroke-width="5")
</template>

<style lang="scss">
@import 'index';
</style>
