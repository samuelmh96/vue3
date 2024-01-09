<template>
    <div>welcome</div>
</template>
<script lang="ts" setup>
import { onMounted, onUpdated } from 'vue';

onMounted(() => {
    console.log('onMounted');
    
})
onUpdated(() => {
    console.log('OnUpdatedkk');
    
})
</script>

<style scoped>
</style>