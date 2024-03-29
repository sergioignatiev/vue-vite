<script setup>
const props=defineProps(['name','homeworld','height','mass'])

</script>
<template>
    <p class="swapi">Hello i am {{ name }} and i am from {{ homeworld }}</p>
    <p class="swapi">My Height {{ height }} {{ mass }}</p>
    <a :href="homeworld" target="_blank">Homeworld</a>
</template>
<style>
.swapi{
    font-size: 20px;
    background-color: blue;
    color:white;
}
</style>
