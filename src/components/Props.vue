<script>
export default{
    data(){
        return{

        }
    },
    props:{
    propValue:{
        type : String,
        default : "prop Values defalut",
        required:true
    },
    UserName:{
        type : Boolean,
        default : "Username",
        required:true
    },
}


}


</script>
<template>
    <div>
        
        <p>{{ propValue }}</p>
        <p>{{ UserName}}</p>
        
    </div>

</template>