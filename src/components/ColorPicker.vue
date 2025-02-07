<script>
export default {
  data() {
    return {
      colorPicker: "", 
      toggleSwitch: false, 
    };
  },
  emits: ["picker"], 
  watch: {
    colorPicker() {
      this.$emit("picker", this.colorPicker); 
    },
  },
};
</script>

<template>
   <strong>Choose your color</strong><br>
  <select v-model="colorPicker">
    <option value="red">Red</option>
    <option value="blue">Blue</option>
    <option value="yellow">Yellow</option>
    <option value="green">Green</option>
  </select>
</template>
