<template>
    <div>
    <div class="ui selection dropdown">
        <input name="gender" type="hidden">
        <i class="dropdown icon"></i>
        <div class="default text">科目</div>
        <div class="menu">
            <div class="item" data-value="1">微积分</div>
            <div class="item" data-value="0">大学物理</div>
        </div>
    </div>
    <div class="ui selection dropdown">
        <input name="gender" type="hidden">
        <i class="dropdown icon"></i>
        <div class="default text">题型</div>
        <div class="menu">
            <div class="item" data-value="1">选择题</div>
            <div class="item" data-value="0">解答题</div>
        </div>
    </div>
    <div class="ui selection dropdown">
        <input name="gender" type="hidden">
        <i class="dropdown icon"></i>
        <div class="default text">知识点</div>
        <div class="menu">
            <div class="item" data-value="1">导数</div>
            <div class="item" data-value="0">积分</div>
        </div>
    </div>
    <div class="ui selection dropdown">
        <input name="gender" type="hidden">
        <i class="dropdown icon"></i>
        <div class="default text">难度系数</div>
        <div class="menu">
            <div class="item" data-value="1">0.1</div>
            <div class="item" data-value="0">0.2</div>
            <div class="item" data-value="1">0.3</div>
        </div>
    </div>
    <button class="ui grey button"> <i class="search icon"></i>搜索</button>
    </div>
</template>
<style>
    .ui.selection.dropdown{
        margin-right: 14px;
        margin-top: 14px;
        margin-bottom: 14px;
        width:100px;
        height:35px;
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
        ready:function () {
            $(".ui.selection.dropdown").dropdown();
        }
    }
</script>