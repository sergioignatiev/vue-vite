<script setup>
import{ref,onMounted} from 'vue'
import { store } from './StoreCount.js'
import AboutEmit from '@/components/AboutEmit.vue';
function myClick(){
  alert("It Works")
}
function mySecondClick(){
  alert("It ALso Works")
}
let number=store.number
let pushInput=''
let input=ref('null')
let onMountedText=ref(null)

onMounted(()=>{
  input.value.focus()
  onMountedText.value.innerHTML="TEXT IS MOUNTED already"
  onMountedText.value.classList.add('text-[red]','text-2xl')
})
</script>

<template>
  <h1 ref="onMountedText">onMountedText </h1>
  <input type="text" ref="input" v-model="pushInput">
  <button @click="store.number.push(pushInput)">SUBMIT </button>
  <div>
    <AboutEmit  @test="myClick">My Button</AboutEmit>
    <AboutEmit class="m-[20px]" @test="mySecondClick">The other button</AboutEmit>
    <h1 v-for="i in store.number">storeNumber:{{ i }}</h1>
    <button @click="store.count++">
      From A: {{ store.count }}
    </button>
  </div>
</template>

