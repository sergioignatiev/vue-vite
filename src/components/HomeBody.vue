<script setup>
import HomeBodyChild from './HomeBodyChild.vue';
const props=defineProps(['pas'])

</script>
<template>
    <h1>:{{ pas }}</h1>
   <HomeBodyChild :passingProps="pas"/>
    <h1>This is Body</h1>
</template>