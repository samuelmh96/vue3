<template>
    <div v-if="note < 55">
        No pasaste
    </div>
    <div v-else>
        Pasastes
    </div>
</template>

<script setup lang="ts">
let note = 55;
</script>

<style scoped>
    
</style>