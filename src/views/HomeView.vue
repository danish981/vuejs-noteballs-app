<template>
  <div class="home">
    <div>
      <button @click="decreaseCounter" class="btn">-</button>
      <span class="counter"> {{ counter }} </span>
      <button @click="increaseCounter" class="btn">+</button>
    </div>
  </div>
</template>

<!-- first type of composition API code to write script -->

<script>

import {ref} from 'vue'

export default {
  setup() {
    const counter = ref(0)

    function increaseCounter() {
      counter.value++;
    }

    function decreaseCounter() {
      counter.value--;
    }

    return {
      counter, increaseCounter, decreaseCounter
    }

  }
}
</script>

<!--<script>-->
<!--export default {-->
<!--  data() {-->
<!--    return {-->
<!--      counter: 0-->
<!--    }-->
<!--  },-->
<!--  methods: {-->
<!--    increaseCounter() {-->
<!--      this.counter++;-->
<!--    },-->
<!--    decreaseCounter() {-->
<!--      this.counter&#45;&#45;;-->
<!--    }-->
<!--  }-->
<!--}-->
<!--</script>-->

<style>
.home {
  text-align: center;
  padding: 20px;
}

.btn, .counter {
  font-size: 40px;
  margin: 10px;
}
</style>