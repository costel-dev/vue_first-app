<template>
  <div class="hello">
    <div>
      <input type="number" v-bind:value="numberInput" />
    </div>
  </div>
</template>

<script>
export default {
  name: "NumberInput",
  props: ["numberInput"],
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped></style>
