<script>
export default {
  data() {
    return {
      toggleSwitch: false, 
    };
  },
  emits: ['toggleON', 'toggleOff'],
  watch: {
    toggleSwitch(newValue) {
      if (newValue) {
        this.$emit('toggleON', newValue); 
      } else {
        this.$emit('toggleOff'); 
      }
    },
  },
};
</script>

<template>
  <input type="checkbox" v-model="  toggleSwitch" />
</template>
