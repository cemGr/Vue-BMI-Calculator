<script setup>
import {computed,ref } from 'vue'

defineProps({
  msg: {
    type: String,
    required: true
  },
  count: {
    type: Number,
    required: true
  }
})

var counter = ref(6)
function  addAnValue(val) {
  //counter++
  counter.value= Number(counter.value)+1
  console.log("howdy")
  console.log(counter.value)
  return counter.value + Number(val)
}

const tester = computed (()=> {
  return counter
})

</script>

<template>
  <div class="greetings">
    <h1 class="green">{{msg}}{{count}}-{{addAnValue(count)}}--{{tester}}</h1>
    <h3>
      You’ve successfully created a project with
      <a target="_blank" href="https://vitejs.dev/">Vite</a> +
      <a target="_blank" href="https://vuejs.org/">Vue 3</a>.
    </h3>
  </div>
</template>

<style scoped>
h1 {
  font-weight: 500;
  font-size: 2.6rem;
  top: -10px;
}

h3 {
  font-size: 1.2rem;
}

.greetings h1,
.greetings h3 {
  text-align: center;
}

@media (min-width: 1024px) {
  .greetings h1,
  .greetings h3 {
    text-align: left;
  }
}
</style>
