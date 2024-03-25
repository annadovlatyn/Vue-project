<script setup>
import HelloWorld from './components/HelloWorld.vue'
import TheWelcome from './components/TheWelcome.vue'
import {ref} from 'vue'

let count = ref(0);
function plusOne(){
  count.value++;
}
function plusTen(){
  count.value += 10
}
function minusOne(){
  count.value--
}
function minusTen(){
  count.value -= 10
}
function reset(){
  count.value = 0;
}
</script>

<template>
  <header>
    <img alt="Vue logo" class="logo" src="./assets/logo.svg" width="125" height="125" />

    <div class="wrapper">
      <HelloWorld msg="You did it!" />
    </div>
  </header>

  <main>
    <h2> {{count}}</h2>
    <button @click="plusOne()" class="btn">+1</button>
    <button @click="plusTen()" class="btn">+10</button>
    <button @click="minusOne()" class="btn">-1</button>
    <button @click="minusTen()" class="btn">-10</button>
    <button @click="reset()" class="btn">Reset</button>
  </main>
</template>

<style scoped>
header {
  line-height: 1.5;
}

.logo {
  display: block;
  margin: 0 auto 2rem;
}
.btn {
  width: 70px;
  margin: 10px 5px;
}

@media (min-width: 1024px) {
  header {
    display: flex;
    place-items: center;
    padding-right: calc(var(--section-gap) / 2);
  }

  .logo {
    margin: 0 2rem 0 0;
  }

  header .wrapper {
    display: flex;
    place-items: flex-start;
    flex-wrap: wrap;
  }
}
</style>
