<script lang="ts">
export default {
  name: 'app-custom-select-demo'
};
</script>
<script setup lang="ts">
import { ref } from 'vue';
import AppCustomSelect from '../index.vue';

const selectedValue = ref('');
const selectedValue2 = ref('');
const selectedValue3 = ref('');
const options = ref([
  { label: 'Default', value: 'default', disabled: true },
  { label: 'Spain', value: 'spain' },
  { label: 'France', value: 'france' },
  { label: 'Italy', value: 'italy' }
]);
</script>

<template lang="pug">
.app-custom-select-demo 
    app-custom-select(
    v-model="selectedValue", 
    :options="options", 
    inputName="selectOne", 
    :outlinedLabel="true")

    app-custom-select(
    v-model="selectedValue2", 
    :options="options", 
    inputName="selectOne", 
    :floatingLabel="true")

    app-custom-select(
    v-model="selectedValue3", 
    :options="options", 
    inputName="selectOne", 
    :floatingLabel="true", 
    :borderBottom="true")
</template>

<style lang="scss">
.app-custom-select-demo {
    .app-custom-select {
        margin-bottom: 3rem;
    }
}
</style>
