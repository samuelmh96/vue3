<template>
    <h1>Fruits</h1>
    <ul>
        <li v-for="fruit in fruits" :key="fruit.id">{{ fruit.name }}</li>
    </ul>
</template>
<script setup lang="ts">
import { Ref, ref } from 'vue';
interface Fruit {
  id: number;
  name: string;
  color: string;
}

let fruits: Ref<Array<Fruit>> = ref([
    {
        id: 1, name: "apple", color: "red"
    },
    {
        id: 2, name: "banana", color: "yellow"
    },
    {
        id: 3, name: "orange", color: "orange"
    },
    {
        id: 4, name: "strawberry", color: "red"
    },
    {
        id: 5, name: "grape", color: "purple"
    },
    {
        id: 6, name: "watermelon", color: "green"
    },
    {
        id: 7, name: "kiwi", color: "brown"
    },
    {
        id: 8, name: "pineapple", color: "yellow"
    },
    {
        id: 9, name: "mango", color: "orange"
    },
    {
        id: 10, name: "pear", color: "green"
    },
]);
</script>

<style scoped>

</style>