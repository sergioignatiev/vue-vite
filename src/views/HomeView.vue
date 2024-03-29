<script setup>
import {store} from './StoreCount.js'
import { provide,ref,computed,reactive } from 'vue';
import HomeHeader from '@/components/HomeHeader.vue';
import HomeBody from '@/components/HomeBody.vue';
import HomeSetup from '@/components/HomeSetup.vue';

const message = ref('hello')
const nome=ref("SergioIgnatievff")

provide('message', message)
provide('nome',nome)

let number=ref(1)
let api=ref([])
let changeVisibility=ref(true)
let redBackground=ref(true)
function addValue(){
  api.value.push({id:number.value,key:api.value.length+1,vis:changeVisibility.value})
  changeVisibility.value=true
}
let reversedArray=computed(()=>{
  return [...api.value].reverse()
})

</script>

<template>

  <main>
    <p>{{ store.number }}</p>
    <button @click="store.increment()">
    From B: {{ store.count }}
    
  </button>
 <div @click="store.number='This is thenewText'" class="text-[30px] text-[red]"> {{ store.number }}</div>
<form @submit.prevent="addValue">
  <label for="">
    <input type="checkbox" v-model="changeVisibility">
    changeVisibility
  </label>

<input class="width-[200px] border-[1px] border-[black] rounded-lg p-2" min="0" max="62" type="number" v-model="number">

</form>

  <HomeHeader   v-for="x in reversedArray" :key="x.key" :number="x.id"><span :class="{blck:x.vis}">{{ x.vis }}</span></HomeHeader>

  
  </main>
</template>
<style>
.blck{
  background-color: red;
}
input[type=checkbox]{
  width: 40px;
  height: 40px;
 
}
input[type=checkbox]:enabled:checked{
 background-color: black !important;
}
</style>
