<script setup>
import { inject } from 'vue'

const message = inject('message')
const nome=inject("nome")
const props=defineProps(['passingProps'])
</script>
<template>
<h1>This {{ nome }} {{ message }} :{{ passingProps }}</h1>

</template>