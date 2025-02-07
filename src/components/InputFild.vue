<template>
    <slot></slot>
    <input :class="{ 'valide-style': isValid }" :type="inputType" v-model="inputValue" />
  </template>
  
  <script>
  export default {
    data() {
      return {
        inputValue: '',
      }
    },
    emits: ['inputValue'],
    props: {
      inputType: {
        type: String,
        default: 'text',
      },
      isValid: {
        type: Boolean,
        default: false,
      },
    },
    watch: {
      inputValue() {
        this.$emit('inputValue', this.inputValue)
      },
    },
  }
  </script>
  
  <style scoped>
  .valide-style {
    border: 2px solid red;
  }
  </style>
  