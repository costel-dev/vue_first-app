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
  props: ["numberInput", "pkey"],
  data() {
    return { inputValue: this.numberInput };
  },
  watch: {
    inputValue: function(newValue) {
      console.log(newValue, this.pkey);
      this.$emit("on-update", newValue, this.pkey);
    },
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped></style>
