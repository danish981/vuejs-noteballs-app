<template>
  <div class="home">

    <h3>{{ counterTItle }}</h3>

    <div>
      <button @click="decreaseCounter" class="btn">-</button>
      <span class="counter"> {{ counter }} </span>
      <button @click="increaseCounter" class="btn">+</button>
    </div>

    <div class="edit">
      <input v-model="counterTItle" type="text">
    </div>

  </div>
</template>

<script setup>
import {ref} from "vue";

const counter = ref(0)
const counterTItle = ref('counter title')

const increaseCounter = () => {
  counter.value++
}

const decreaseCounter = () => {
  counter.value--
}

</script>

<style>
.home {
  text-align: center;
  padding: 20px;
}

.btn, .counter {
  font-size: 40px;
  margin: 10px;
}

.edit {
  margin-top: 50px;
}

</style>