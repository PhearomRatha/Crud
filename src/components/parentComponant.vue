
<script>
import ChildComponant from './ChildComponant.vue';
export default {
  components: {
    ChildComponant
  },
  data(){
    return{
      counter:0
    }
  },

  provide() {
    return {
      msg:""
    
    };
  },
  inject:['counterInject'],

  emits:['btn-click'],
  methods:{
    onclickBtn(){
            this.counter++
            this.$emit('btn-clicked',this.counter)
        }
  }
}
</script>


<template>
  <div>
    <h1>Parent of child</h1>
    {{  counterInject }}
    <ChildComponant></ChildComponant>
  </div>
</template>







