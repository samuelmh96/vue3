<template>
    <div>welcome</div>
</template>
<script lang="ts">
import { defineComponent } from 'vue';

export default defineComponent({
    name: "CycleOption",
    created() {
        console.log("Created");
    },
    mounted() {
        console.log('mounted');
    },
    updated() {
        console.log('Updated');
    },
    unmounted() {
        console.log('Unmounted');
    },
})
     
</script>

<style scoped>
</style>