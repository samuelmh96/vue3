<template>
    <div class="post">
        <h3>{{title}}</h3>
        <p>{{content}}</p>
        <input type="text" v-model="message">
        <button @click="handleClick()">aceptar</button>
    </div>
</template>
<script lang="ts" setup>
import { Ref, ref, defineProps, defineEmits } from 'vue';

const props = defineProps({
    'title': String,
    'content': String
});
const emit = defineEmits(['sayHi']);
const handleClick = () => {
    emit('sayHi', message.value);
}
let message: Ref<string> = ref('')
</script>

<style scoped>
.post {
    width: 300px;
    height: 200px;
    border-radius: 10px;
    background-color: #92c7a3;
    margin: 10px;
    padding: 10px;
    box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
    overflow: hidden;
    transform: scale(1);
    transition: transform 0.3s ease-in-out;
}

.post:hover {
    transform: scale(1.05);
}

.post h3 {
    color: #4d7c4c;
    margin-bottom: 8px;
    transition: color 0.3s ease-in-out; 
}

.post:hover h3 {
    color: #2c5e35; 
}

.post p {
    color: #333; 
    transition: color 0.3s ease-in-out;
}

.post:hover p {
    color: #555;
}
</style>