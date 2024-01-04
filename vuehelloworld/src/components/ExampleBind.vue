<template>
   <p :class="{'danger' : hasError}">Datos enviados correctamente.</p>
   <p :style="{backgroundColor:'#DDFF', color:c}">Datos enviado incorrectamente</p>
   <button @click="handleClick()">Cambiar Color</button>
</template>
<script setup lang="ts">
import {ref} from 'vue';
let hasError = ref(true);
let c = ref('#AAFF')
const handleClick = () => {
    c.value = c.value === '#FF0' ? '#AAFF' : '#FF0'
}
</script>

<style>
.danger{
    color: red;
}
</style>