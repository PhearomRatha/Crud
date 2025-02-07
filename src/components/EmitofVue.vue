<script>
export default{
    data(){
        return{
            
        }
    },

    emits:['btn-click'],
    methods:{
        onclickBtn(){
            this.$emit('btn-clicked')
        }
    }
}

</script>
<template>
    <button @click="onclickBtn">Button</button>
    {{ counter }}
</template>