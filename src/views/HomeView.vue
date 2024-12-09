<template>
  <div class="home">

    <h2>{{ oddOrEven }}</h2>

    <h3>{{ counterData.title }}</h3>

    <div>
      <button @click="decreaseCounter(2)" class="btn">--</button>
      <button @click="decreaseCounter(1)" class="btn">-</button>
      <span class="counter"> {{ counterData.count }} </span>
      <button @click="increaseCounter(1, $event)" class="btn">+</button>
      <button @click="increaseCounter(2, $event)" class="btn">++</button>
    </div>

    <div class="edit">
      <input v-model="counterData.title" type="text">
    </div>

  </div>
</template>

<script setup>
import {computed, reactive} from "vue";

const counterData = reactive({
  count: 0,
  title: 'my counter'
})

const increaseCounter = (amount, e) => {
  console.log(e)
  counterData.count += amount
}

const decreaseCounter = (amount) => {
  counterData.count -= amount
}

const oddOrEven = computed(() => {
  return (counterData.count % 2 === 0) ? 'even' : 'odd'
})

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