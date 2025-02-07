<script>
import { useTransitionState, watch } from 'vue'

export default {
  data() {
    return {
      userName: '',
    }
  },

  emits: ['inpuChange'],
  watch:{
    userName() {
        this.$emit('inpuChange',this.userName)
        
      },
  }
  
}
</script>
<template>
  <input type="text" v-model="userName" @input= "userName" 
    placeholder="Please input your name..." />
 
</template>
