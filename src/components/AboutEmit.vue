<script setup>

</script>
<template>
   
    <button
    class="px-[20px] py-[7px] rounded-lg bg-slate-300 hover:bg-slate-400 hover:text-white"
    @click="$emit('test')"><slot></slot></button>
</template>