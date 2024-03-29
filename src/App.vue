<script setup>
import { RouterLink, RouterView } from 'vue-router'

</script>

<template>
  <header>
  

    <div class="wrapper">
     

      <nav>
        <RouterLink class='routerLink'to="/">Home</RouterLink>
        <RouterLink class='routerLink'to="/about">About</RouterLink>
      </nav>
    </div>
  </header>
<main>
  <RouterView />
</main>
</template>

<style >
*{
  margin: 0;
  padding:0;
}
nav{
  background: grey;
}
a{
  font-family: 'Courier New', Courier, monospace;
  display:inline-block;
  padding:0px 10px;
  text-decoration: none;

}
a.router-link-active{
  color:red;
}
main{
  padding: 0px 20px;
}
</style>
