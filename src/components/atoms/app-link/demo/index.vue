<script lang="ts">
export default {
  name: 'app-link-demo'
};
</script>
<script setup lang="ts">
import { ref } from 'vue';
import AppLink from '../index.vue';

const icon = ['fa-solid', 'fa-house'];
const links = ref([
  {
    name: 'TEST',
    text: 'Link 1 sin icono',
    params: { id: '12' },
    query: { shoping: 123 }
  },
  {
    name: 'TEST',
    params: { id: '1235' },
    text: 'Link 2 con icono a la derecha',
    icon: icon
  },
  {
    path: '/test/:1',
    text: 'Link 3 con icono a la izquierda',
    icon: icon,
    iconPosition: 'left'
  },
  {
    path: '/test/:2',
    text: 'Link 4 con icono abajo',
    icon: icon,
    iconPosition: 'top'
  },
  {
    path: '/test/:3',
    query: { shoping: 123 },
    text: 'Link 5 con icono arriba',
    icon: icon,
    iconPosition: 'bottom'
  },
  {
    path: '/test/:1',
    icon: icon
  },
]);
</script>

<template lang="pug">
.app-link-demo 
    div(
    v-for="(item, index) in links", 
    :key="index")
        app-link(
        :path="item.path", 
        :routeName="item.name"
        :params="item.params", 
        :queryParams="item.query"
        :text="item.text", 
        :icon="item.icon", 
        :iconPosition="item.iconPosition")
</template>

<style lang="scss">
.app-link-demo {
    display: flex;
    flex-direction: column;
    gap: 20px;

    div {
        padding: 0.75rem;
        background-color: var(--secondary-grey);
    }
}
</style>
