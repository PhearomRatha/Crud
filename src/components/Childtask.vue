<template>
  <div>
    <h2>Child Component</h2>
  
  </div>
</template>

<script>
export default {
  props: {
    stepSize: {
      type: Number,
      required: true,
    },
  },
  data() {
    return {
      currentValue: 0, 
    };
  },
  emits: ['value-updated'],
  methods: {

    increment() {
      this.currentValue += this.stepSize;
      this.emitValue();
    },
  
    decrement() {
      this.currentValue -= this.stepSize;
      this.emitValue();
    },

    emitValue() {
      this.$emit('value-updated', this.currentValue);
    },
  },
};
</script>
