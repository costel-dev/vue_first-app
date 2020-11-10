<template>
  <div class="hello">
    <div>
      <input type="number" v-model="inputValue" />
    </div>
  </div>
</template>

<script>
export default {
  name: "NumberInput",
  props: ["numberInput"],
  data() {
    return { inputValue: this.numberInput };
  },
  watch: {
    inputValue: function(newValue) {
      this.inputValue = newValue;
      console.log(this.inputValue);
    },
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped></style>
