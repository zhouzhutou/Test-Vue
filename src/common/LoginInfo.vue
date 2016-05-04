<template>
  <div class="currentUser">当前用户:<span>{{name}}</span>&nbsp;&nbsp;权限:<span>{{$route.query.role}}</span></div>
</template>
<style>
   .currentUser{
       float: right;
       font-size: 14px;
       color: darkgray;
   }
    .currentUser span{
        font-size: 13px;
        font-weight: 600;
        font-family: "微软雅黑";
    }
</style>
<script>

    export default{
        data(){
            return{
                name:'hello vue',
                right:"普通管理员"
            }
        },
        components:{

        }
    }
</script>