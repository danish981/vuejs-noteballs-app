<template>
  <div class="home">

    <h3>{{ counterData.title }}</h3>

    <div>
      <button @click="decreaseCounter" class="btn">-</button>
      <span class="counter"> {{ counterData.count }} </span>
      <button @click="increaseCounter" class="btn">+</button>
    </div>

    <div class="edit">
      <input v-model="counterData.title" type="text">
    </div>

  </div>
</template>

<script setup>
import {reactive} from "vue";

const counterData = reactive({
  count: 0,
  title: 'my counter'
})

const increaseCounter = () => {
  counterData.count++
}

const decreaseCounter = () => {
  counterData.count--
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