<template>
    <div>
        <button @click="prevPage" :disable="activePage === 1">PREVIOUS</button>

        <button v-for="page in pages" :key="page" class="" >{{ page }}</button>

        <button @click="nextPage" :disable="activePage === pages">NEXT</button>
    </div>
</template>
<script setup>
import { ref } from 'vue'
const pages = ref(10)
const activePage = ref(2)

const prevPage = () => {
    if (activePage.value > 1) {
        activePage.value--
    }
}

const nextPage = () => {
    if (activePage.value < pages.value) {
        activePage.value++
    }
    console.log(activePage.value)
}


</script>