<script>
export default{
    data(){
        return{

        }
    },
    props:{
        counter:{
            type: Number,
            default:0


        }

    },
    emits:['clickMe'],
    methods:{
        onclick(){
            this.$emit('clickMe')
        }

    }
}
</script>
<template>
<button @click="onclick">Click</button>

</template>