<template>
  <div class="home">
    <h2 class="status">{{ oddOrEven }}</h2>

    <h3 class="title">{{ counterData.title }}</h3>

    <div class="counter-container">
      <button @click="decreaseCounter(2)" class="btn btn-decrease">--</button>
      <button @click="decreaseCounter(1)" class="btn btn-decrease">-</button>
      <span class="counter">{{ counterData.count }}</span>
      <button @click="increaseCounter(1, $event)" class="btn btn-increase">+</button>
      <button @click="increaseCounter(2, $event)" class="btn btn-increase">++</button>
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
  transition: background-color 0.3s, transform 0.2s; /* Added transform for effect */
}

.btn:hover {
  background-color: #0056b3;
}

.btn-decrease:hover {
  transform: scale(1.1); /* Slightly enlarge on hover */
}

.btn-increase:hover {
  transform: scale(1.1); /* Slightly enlarge on hover */
}

.counter {
  font-size: 40px;
  margin: 0 20px;
  padding: 10px;
  border-radius: 5px;
  color: #007BFF;
  background-color: #e7f3ff;
  border: 2px solid #007BFF;
  box-shadow: inset -2px -2px rgba(255, 255, 255, 0.5), inset -4px -4px rgba(255, 255, 255, 0.3); /* Inner shadow for depth */
}

.edit {
  margin-top: 20px;
}

.edit input {
  padding: 10px;
  font-size: 16px;
  border-radius: 5px;
  width: 100%;
  max-width: 300px;
  border: none;
  box-shadow: 0px -2px rgba(0, 0, 0, 0.1), inset -1px -1px rgba(255, 255, 255, 0.5); /* Inner shadow for depth */
  transition: border-color .3s;
}

.edit input::placeholder {
  color: #aaa; /* Placeholder color */
}

.edit input:hover,
.edit input:focus {
  outline: none;
  box-shadow: none; /* Remove shadow on focus */
  border-bottom: gray;
  border-color: #007BFF; /* Add underline on focus */
}
</style>
