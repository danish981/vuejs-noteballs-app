<template>
  <div class="home">
    <h2 class="status">{{ oddOrEven }}</h2>

    <h3 class="title">{{ counterData.title }}</h3>

    <div class="counter-container">
      <button @click="decreaseCounter(2)" class="btn">--</button>
      <button @click="decreaseCounter(1)" class="btn">-</button>
      <span class="counter">{{ counterData.count }}</span>
      <button @click="increaseCounter(1, $event)" class="btn">+</button>
      <button @click="increaseCounter(2, $event)" class="btn">++</button>
    </div>

    <div class="edit">
      <input v-model="counterData.title" type="text" placeholder="Enter counter title"/>
    </div>
  </div>
</template>

<script setup>
import {computed, reactive} from "vue";

const counterData = reactive({
  count: 0,
  title: 'My Counter'
});

const increaseCounter = (amount, e) => {
  console.log(e);
  counterData.count += amount;
};

const decreaseCounter = (amount) => {
  counterData.count -= amount;
};

const oddOrEven = computed(() => {
  return (counterData.count % 2 === 0) ? 'Even' : 'Odd';
});
</script>

<style>
body {
  background-color: #f0f4f8;
  font-family: 'Arial', sans-serif;
}

.home {
  text-align: center;
  padding: 40px;
  border-radius: 10px;
  box-shadow: 0 4px 20px rgba(0, 0, 0, 0.1);
  background-color: #ffffff;
  max-width: 400px;
  margin: 50px auto;
}

.status {
  font-size: 24px;
  color: #333;
  margin-bottom: 20px;
}

.title {
  font-size: 28px;
  color: #007BFF;
  margin-bottom: 30px;
}

.counter-container {
  display: flex;
  align-items: center;
  justify-content: center;
  margin-bottom: 30px;
}

.btn {
  font-size: 24px;
  margin: 0 10px;
  padding: 10px 20px;
  border: none;
  border-radius: 5px;
  background-color: #007BFF;
  color: white;
  cursor: pointer;
  transition: background-color 0.3s;
}

.btn:hover {
  background-color: #0056b3;
}

.counter {
  font-size: 40px;
  margin: 0 20px;
  padding: 10px 20px;
  border: 2px solid #007BFF;
  border-radius: 5px;
  color: #007BFF;
  background-color: #e7f3ff;
}

.edit {
  margin-top: 20px;
}

.edit input {
  padding: 10px;
  font-size: 16px;
  border: 2px solid #007BFF;
  border-radius: 5px;
  width: 100%;
  max-width: 300px;
  transition: border-color 0.3s;
}

.edit input:focus {
  border-color: #0056b3;
  outline: none;
}
</style>