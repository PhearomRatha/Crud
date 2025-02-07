<template>
    <div>
      <h2>Child Component</h2>
      <p>Current Value: {{ currentValue }}</p>
      <button @click="increment">Increase</button>
      <button @click="decrement">Decrease</button>
 
    </div>
  </template>
  
  <script>
  export default {
    data() {  
      return {
        currentValue: 0, 
      };
    },
    props: {
      step_Size: {
        type: Number,
        required: true,
      },
    },
    emits: ['value-updated'],
    methods: {
      emitValue() {
        this.$emit('value-updated', this.currentValue);
      },
 
      increment() {
        this.currentValue += this.step_Size;
        this.emitValue();
      },
    
      decrement() {
        this.currentValue -= this.step_Size;
        this.emitValue();
      },

   
    },
 
  };
  </script>
  