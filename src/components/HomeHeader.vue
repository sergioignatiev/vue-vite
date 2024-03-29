<script setup>
import {ref,onMounted} from 'vue'
import HomeApi from './HomeApi.vue';
let header=ref("HomeHeader")
let swapi=ref('')
const props=defineProps(['name','number'])


onMounted(()=>{
  (async function(){
    const response=await fetch(`https://swapi.dev/api/people/${props.number}`)
 swapi.value= await response.json()
   }())
  
})
</script>
<template>
<HomeApi :name="swapi.name"
 :homeworld="swapi.homeworld"
  :height="swapi.height"
  :mass="swapi.mass"
  />
    <p>Hello,{{ number }} my name is {{ swapi.name }} and i am from {{ swapi.homeworld }}</p>
   
    
    
    <slot></slot>

<h1>{{ header }} {{ name }}</h1>

</template>