<template>
    <div id="listMenu">
    <div class="ui styled fluid accordion">
        <div class="title"><i class="dropdown icon"></i> 题库管理 </div>
        <div class="content">
            <!--<div class="ui styled accordion innerList">-->
                <!--<div class="title"> <a>题目浏览</a> <i class="list layout icon"></i> </div>-->
                <!--<div class="title"> <a>题目添加</a> <i class="plus square outline icon"></i></div>-->
            <!--</div>-->
            <ul>
                <li class="pre"><i class="align justify icon"></i><a v-link="{ name:'problemList',exact:true }" >题目浏览</a> </li>
                <li><i class="plus square outline icon"></i><a v-link="{ name:'problemAdd',exact:true }">题目添加</a></li>
            </ul>
        </div>
        <div class="title"><i class="dropdown icon"></i> 试卷生成</div>
        <div class="content">
            <ul>
                <li class="pre"><i class="add circle icon"></i><a v-link="{name:'paperAuto',exact:true}" >试卷自动生成</a></li>
                <li><i class="pointing up icon"></i><a v-link="{name:'paperMan',exact:true}" >试卷手动生成</a></li>
            </ul>
        </div>
        <!--<div class="title"><i class="dropdown icon"></i>模拟考试</div>-->
        <!--<div class="content">-->
            <!--<ul>-->
                <!--<li><i class="edit icon"></i><a href="#">开始考试</a></li>-->
            <!--</ul>-->
        <!--</div>-->
        <div class="title"><i class="dropdown icon"></i> 试卷生成</div>
        <div class="content">
            <ul>
                <li class="pre"><i class="list icon"></i><a v-link="{ path:'/testHome/users/',exact:true }">用户列表</a></li>
                <!--<li><i class="add user icon"></i><a href="#">用户添加</a></li>-->
            </ul>
        </div>
    </div>
    </div>
    <!--<router-view transition-mode="out-in" transition="fade"></router-view>-->
</template>

<style>
    #listMenu{
        padding: 0px;
        height: 500px;
        border: 1px black solid;
        /*border-radius: 6px;*/
    }

    #listMenu .ui.styled.accordion>.title {
        color: dodgerblue;
        background-color: papayawhip;
        font-family:"微软雅黑";
        height:32px;

    }
    #listMenu .ui.styled.accordion .content{
        padding:0px;
        margin:0px;
        /*background-color: black;*/
    }
    #listMenu .ui.styled.accordion .content ul{
        padding:0px;
        margin:0px;
        /*background-color: black;*/
    }
    #listMenu .ui.styled.accordion .content ul li{
        height:30px;
        padding-top:6px;
        padding-bottom: 6px;
        padding-left: 12px;
    }
    #listMenu .ui.styled.accordion .content ul .pre{
        border-bottom: black 1px solid;
    }
    #listMenu .ui.styled.accordion .content ul li a{
        font-size: 14px;
        color: #000000;
        font-family: 'Lato', 'Helvetica Neue', Arial, Helvetica, sans-serif;

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

        },
        ready:function(){
          $(".ui.accordion").accordion();
        }
    }
</script>