<template>
<div class="ui centered grid">
    <div class="row" >
        <div class="ten wide column">
            <test-head></test-head>
        </div>
        <div class="ten wide column" style="margin-top: 30px">
            <exam></exam>
        </div>
    </div>
</div>
</template>
<style>

</style>
<script>
    var testHead=require("./components/TestHead.vue");
    var exam=require("./components/Exam.vue");
    export default{
        data(){
            return{
                msg:'hello vue'
            }
        },
        components:{
            testHead:testHead,
            exam:exam
        }
    }
</script>