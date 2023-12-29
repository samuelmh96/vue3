<template>    
<h2>Counter Option</h2>    
    <h3>{{ counter }}</h3>
    <button @click="increment">+1</button>
</template>

<script lang="ts">
import { defineComponent } from 'vue';
export default defineComponent({
    name: 'CounterOption',
    data() {
        let counter = 0;
        return {
            counter
        }
    },
    methods: {
        increment() {
            this.counter++;
        }
    },
    });

</script>

<style>
</style>