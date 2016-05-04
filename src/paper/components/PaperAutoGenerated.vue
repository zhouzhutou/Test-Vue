<template>
    <auto-nav nav-item="试卷自动生成"></auto-nav>

    <form class="ui form">
        <h4 class="ui header">试卷自动生成</h4>
        <div class="six wide field">
            <label>试卷名称</label>
            <input placeholder="试卷名称" type="text">
        </div>
        <div class="fields">
        <div class="field">
            <label>科目</label>
            <div class="ui selection dropdown">
                <div class="default text">科目</div>
                <i class="dropdown icon"></i>
                <input name="subject" type="hidden">
                <div class="menu">
                    <div class="item" data-value="1">微积分</div>
                    <div class="item" data-value="2">线性代数</div>
                    <div class="item" data-value="3">C++程序设计</div>
                    <div class="item" data-value="4">Java程序设计</div>
                </div>
            </div>
        </div>
        <div class="field">
            <label>总分</label>
            <div class="ui selection dropdown">
                <div class="default text">总分</div>
                <i class="dropdown icon"></i>
                <input name="subject" type="hidden">
                <div class="menu">
                    <div class="item" data-value="1">10</div>
                    <div class="item" data-value="2">50</div>
                    <div class="item" data-value="3">100</div>
                    <div class="item" data-value="4">150</div>
                </div>
            </div>
        </div>
        <div class="field">
                <label>难度</label>
                <div class="ui selection dropdown">
                    <div class="default text">难度</div>
                    <i class="dropdown icon"></i>
                    <input name="subject" type="hidden">
                    <div class="menu">
                        <div class="item" data-value="1">0.1</div>
                        <div class="item" data-value="2">0.2</div>
                        <div class="item" data-value="3">0.3</div>
                        <div class="item" data-value="4">0.4</div>
                        <div class="item" data-value="4">0.4</div>
                    </div>
                </div>
        </div>
        </div>

        <div class="field">
            <label>题型分布</label>
            <div class="three fields">
                <div class="two wide field">
                    <label>选择题</label>
                    <div class="ui compact menu">
                        <div class="ui simple dropdown item">
                            个
                            <i class="dropdown icon"></i>
                            　 <span class="text">0</span>
                            <div class="menu">
                                <div class="item">1</div>
                                <div class="item">2</div>
                                <div class="item">3</div>
                            </div>
                        </div>
                    </div>
                </div>
                <div class="two wide field">
                    <label>判断题</label>
                    <div class="ui compact menu">
                        <div class="ui simple dropdown item">
                           个
                            <i class="dropdown icon"></i>
                           　 <span class="text">0</span>
                            <div class="menu">
                                <div class="item">1</div>
                                <div class="item">2</div>
                                <div class="item">3</div>
                            </div>
                        </div>
                    </div>
                </div>
                <div class="two wide field">
                    <label>论述题</label>
                    <div class="ui compact menu">
                        <div class="ui simple dropdown item">
                            个
                            <i class="dropdown icon"></i>
                            　 <span class="text">0</span>
                            <div class="menu">
                                <div class="item">1</div>
                                <div class="item">2</div>
                                <div class="item">3</div>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>

        <div class="two wide field">
            <label>考试时间</label>
            <input type="text" id="datepicker" size="30">
        </div>

        <button class="ui teal button auto" type="submit">自动生成</button>
        <button class="ui teal button" type="">重置试卷</button>
    </form>
</template>
<style>
    .ui.teal.button{
        margin-top:12px;
    }
    .auto{
        margin-right:12px;
    }
</style>
<script>
    var autoNav=require("../../common/Nav.vue");
    export default{
        data(){
            return{
                msg:'hello vue'
            }
        },
        components:{
            autoNav:autoNav
        },
        ready:function(){
            $(".ui.selection.dropdown").dropdown();
            $(".ui.simple.dropdown.item").dropdown();
            $("#datepicker").datepicker({
                dateFormat:"yy-mm-dd",
                showAnim:"fadeIn"
            });
        }
    }
</script>