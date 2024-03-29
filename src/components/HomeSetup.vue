<script setup>
import {ref} from 'vue'
let name=ref('Sergio')
let count=ref(0)

</script>
<template>
<h1 class="text-[70px]" @click="increaseCount">{{ name }} {{ count }}</h1>

</template>
<style scoped>
</style>