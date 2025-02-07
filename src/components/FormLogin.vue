<script>
import InputFile from './InputFile.vue';
import TaskManager from './taskManager.vue';
import TaskManager from './taskManager.vue';

export default{
    components:{
        InputFile,
        TaskManager
    },
    data() {
        return{
            inputData:'',
            userName:'',
            pws:'',
            
       
        }
    },
    methods:{
        click(){


        }

    }
}
</script>
<template>
    <InputFile @inputChange="userName"  >

        <p>User Input: {{inputData}}</p>
    </InputFile><br>
    <InputFile @inputChange="pws">
    
        <p>User Input: {{inputData}}</p>
    </InputFile>
    <button @click="click">
        submit
    </button>
 


</template>