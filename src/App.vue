<template>
  <div>
    <h1>My First VUE Task</h1>

    <NumberInput
      v-for="(numberInput, idx) in numberInputs"
      :key="idx"
      :pkey="idx"
      :numberInput="numberInput"
      @on-update="updateInput"
    />

    <button @click="addInput">{{ sumOfInputs }}</button>
  </div>
</template>

<script>
import NumberInput from "./components/NumberInput.vue";

export default {
  name: "App",
  components: {
    NumberInput,
  },
  data() {
    return {
      numberInputs: [10, 20, 25, 25, 20],
    };
  },
  methods: {
    addInput() {
      const random = Math.floor(Math.random() * 11);
      return this.numberInputs.push(random);
    },
    updateInput(newInput, indexKey) {
      this.numberInputs.splice(indexKey, 1, +newInput);
      this.numberInputs = [...this.numberInputs];
    },
  },
  computed: {
    sumOfInputs() {
      return this.numberInputs.reduce((total, num) => total + num);
    },
  },
};
</script>

<style>
* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}
body {
  font-family: Arial, Helvetica, sans-serif;
  text-align: center;
  color: #2c3e50;
  margin-top: 50px;
}
h1 {
  margin-bottom: 30px;
}
input,
button {
  margin: 5px;
  padding: 10px;
  text-align: center;
  font-size: 16px;
  width: 300px;
}
</style>
