<script setup>
import { ref } from 'vue';

const val= ref('');
const large = ref(0);

function draw() {
    const words = val.value.split(' ')
    large.value = words.length    
    console.log(words)
}
</script>


<template>
    <h1 class="font-bold text-center ">Ejercicio microbiologia</h1>
    <div class="mx-auto mt-12 w-40">
        <div class="w-4  h-6 inline-block bg-slate-400 mx-1" 
        :class="{'bg-red-500': large > 0 && large < 3}"></div>
        <div class="w-4  h-8 inline-block bg-slate-400 mx-1" 
        :class="{'bg-orange-500': large <=4 && large <= 6}"></div>
        <div class="w-4  h-10 inline-block bg-slate-400 mx-1" 
        :class="{'bg-yellow-500': large <= 3 && large < 7}"></div>
        <div class="w-4  h-12 inline-block bg-slate-400 mx-1" 
        :class="{'bg-green-500': large > 6}"></div>
        <input class="rounded bg-slate-500 font-bold" v-model="val"/> <button @click="draw" class="hover:bg-red-400 bg-red-600 mt-1 rounded">Calcular.</button>
    </div>
</template>