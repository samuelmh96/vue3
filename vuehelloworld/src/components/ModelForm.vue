<template>
    <form action="">
        <input type="text" v-model="inputText">
        <input type="checkbox" v-model="agree"> Acepto los terminos y condiciones
        <select v-model="options">
            <option :value="1" selected>Option 1</option>
            <option :value="2">Option 2</option>
            <option :value="3">Option 3</option>

        </select>
    </form>
    <h3>{{ inputText }}</h3>
</template>

<script setup lang="ts">
import { ref } from 'vue';
let inputText = ref('')
let agree = ref(true)
let options = ref(2)
    
</script>

<style>
</style>