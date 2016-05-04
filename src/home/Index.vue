<template>
   <div class="ui padded aligned grid">
           <div class="sixteen wide column">
               <login-info></login-info>
           </div>
    <div class="row">
       <div class="three wide column">
           <left-bar></left-bar>
       </div>
       <div class="thirteen wide column">
           <title-bar></title-bar>
           <router-view transition-mode="out-in" transition="fade"></router-view>
       </div>
    </div>
   </div>

 </template>

<style>
  /*.header{*/
      /*height: 18px;*/
      /*width: 100%;*/
      /*padding-top: 0px;*/
      /*padding-bottom: 0px;*/
      /*margin-top: 0px;*/
      /*margin-bottom: 0px;*/
  /*}*/
  .sixteen.wide.column{
     height: 18px;
      width: 100%;
      padding-top: 0px;
      padding-bottom: 0px;
  }
  .ui.grid div{
      margin: 0px;
  }
  .fade-transition{
    transition: opacity .5s ease;
  }
 .fade-enter , .fade-leave{
     opacity: 0;
 }
</style>

<script>

   // var leftBarComponent=require("./components/LeftBar.vue");
   // var titleBarComponent=require("./components/TitleBar.vue");
   var loginInfo=require("../common/LoginInfo.vue");
    console.log("hello");
    import LeftBar from './components/LeftBar.vue';
    import TitleBar from './components/TitleBar.vue';
    export default{
        data(){
            return{
                msg:'hello vue'
            }
        },
        components:{
            leftBar: LeftBar,
            titleBar: TitleBar,
            loginInfo:loginInfo
        }
    }
</script>