<template>
    <h2>Counter Composition</h2>
   <h3>{{ counter }}</h3>
   <button @click="increment">+1</button>
</template>

<script lang="ts" setup>
import { ref } from 'vue';

    let counter = ref(0);
    const increment = () => {
        counter.value++;
    }

</script>