<template>
    <div class="head">
      <div class="title"><p>数字化题库与试卷生成系统</p><img src="/static/img/fly.png" style="width:200px;height:128px;vertical-align:middle"></div>
    </div>
</template>
<style>
    .head{
        height:128px;
        border:1px black solid;
        background-color:floralwhite;
    }
    .head .title{
        position: relative;
        padding: 0px;
        font-size: 48px;
        color: #00aced;
        text-shadow: 4px 4px 4px #00ACED;
    }
    .head .title p{
        margin-left: 30px;
        margin-top:30px;
        margin-bottom:30px;
    }
    .head img{
        position: absolute;
        right: 30px;
        bottom:-29px;
    }
</style>
<script>

    export default{
        data(){
            return{
                msg:'hello vue'
            }
        },
        components:{

        }
    }
</script>