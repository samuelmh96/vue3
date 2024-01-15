<template>
    <input type="text" v-model="message">
    <h3>{{ message }}</h3>
    <h3>{{ reverse }}</h3>
</template>
<script lang="ts" setup>
import { computed, ref, Ref } from 'vue';
const message:Ref<string>= ref('');
const reverse = computed(():string => message.value.split('').reverse().join(''))
</script>

<style scoped>
</style>