<template>
<div class="ui middle aligned center aligned grid" style="padding-top:180px ">
<div class="column" style="width: 450px;height: 370px;">
<pass-port></pass-port>
</div>
</div>
</template>
<style>
body{

}
</style>
<script>
    var passPort=require("./components/PassPort.vue");
    export default{
        data(){
            return{
                msg:'hello vue'
            }
        },
        components:{
           passPort:passPort
        }
    }
</script>