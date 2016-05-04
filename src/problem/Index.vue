<template>
<!--<content-nav></content-nav>-->
    <router-view></router-view>
</template>
<style>

</style>
<script>
    var nav=require("./../common/Nav.vue");
    export default{
        data(){
            return{
                msg:'hello vue'
            }
        },
        components:{
//           contentNav:nav
        }
}
</script>