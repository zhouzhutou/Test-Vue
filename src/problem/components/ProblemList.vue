<template>
    <list-nav nav-item="试题列表"></list-nav>
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
    <table class="ui blue table">
        <thead>
        <tr>
            <th>编号</th>
            <th>题目</th>
            <th>科目</th>
            <th>题型</th>
            <th>知识点</th>
            <th>难度</th>
            <th>答案</th>
            <th>操作</th>
        </tr></thead><tbody>
    <tr v-for="problem in pageProblems">
        <td>{{problem.id}}</td>
        <td>{{problem.name}}</td>
        <td>{{problem.subject}}</td>
        <td>{{problem.type}}</td>
        <td>{{problem.knowledgePoints}}</td>
        <td>{{problem.difficulty}}</td>
        <td>{{problem.answer}}</td>
        <td>
            <button class="ui teal button">查看</button>
            <button class="ui teal button">编辑</button>
            <button class="ui teal button">删除</button>
        </td>
    </tr>
    <!--<tr>-->
        <!--<td>3</td>-->
        <!--<td>1+1=?</td>-->
        <!--<td>微积分</td>-->
        <!--<td>判断题</td>-->
        <!--<td>导数</td>-->
        <!--<td>0.2</td>-->
        <!--<td>正确</td>-->
        <!--<td>-->
            <!--<button class="ui teal button">查看</button>-->
            <!--<button class="ui teal button">编辑</button>-->
            <!--<button class="ui teal button">删除</button>-->
        <!--</td>-->
    <!--</tr>-->
    <!--<tr>-->
        <!--<td>4</td>-->
        <!--<td>1+1=?</td>-->
        <!--<td>微积分</td>-->
        <!--<td>选择题</td>-->
        <!--<td>导数</td>-->
        <!--<td>0.4</td>-->
        <!--<td>Ｂ</td>-->
        <!--<td>-->
            <!--<button class="ui teal button">查看</button>-->
            <!--<button class="ui teal button">编辑</button>-->
            <!--<button class="ui teal button">删除</button>-->
        <!--</td>-->
    <!--</tr>-->
    </tbody>
    </table>

        <div class="ui pagination menu">
            <!--<a class="active item">-->
                <!--1-->
            <!--</a>-->
            <!--<div class="disabled item">-->
                <!--...-->
            <!--</div>-->
            <!--<a class="item">-->
                <!--10-->
            <!--</a>-->
            <!--<a class="item">-->
                <!--11-->
            <!--</a>-->
            <!--<a class="item">-->
                <!--12-->
            <!--</a>-->
            <a v-for="n in page.pageCount" class="item" v-on:click="page.currentPage=n+1">
                {{n+1}}
            </a>
        </div>

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
    .ui.blue.table{
        margin-top: 0px;
        padding: 0px;
    }
</style>
<script>
    var listNav=require("./../../common/Nav.vue");
    export default{
        data(){
            return{
               page:{
                    currentPage:0,
                    pageCount:0,
                    perPage:4
                },
               problems:[{
                   id:1,
                   name:"1+1=?",
                   subject:"c语言",
                   type:"选择题",
                   knowledgePoints:"指针",
                   difficulty:"0.2",
                   answer:"A"
               },
                   {
                       id:2,
                       name:"1+1=?",
                       subject:"java",
                       type:"选择题",
                       knowledgePoints:"数组",
                       difficulty:"0.3",
                       answer:"B"
                   },
                   {
                       id:3,
                       name:"1+1=?",
                       subject:"java",
                       type:"选择题",
                       knowledgePoints:"数组",
                       difficulty:"0.3",
                       answer:"B"
                   },
                   {
                       id:4,
                       name:"1+1=?",
                       subject:"java",
                       type:"选择题",
                       knowledgePoints:"数组",
                       difficulty:"0.3",
                       answer:"B"
                   },
                   {
                       id:5,
                       name:"1+1=?",
                       subject:"java",
                       type:"选择题",
                       knowledgePoints:"数组",
                       difficulty:"0.3",
                       answer:"B"
                   },
                   {
                       id:6,
                       name:"1+1=?",
                       subject:"java",
                       type:"选择题",
                       knowledgePoints:"数组",
                       difficulty:"0.3",
                       answer:"B"
                   },
                   {
                       id:7,
                       name:"1+1=?",
                       subject:"java",
                       type:"选择题",
                       knowledgePoints:"数组",
                       difficulty:"0.3",
                       answer:"B"
                   }
               ]
            }
        },
        components:{
            listNav:listNav
        },
        computed: {
            pageProblems: {
                get: function(){
                    var start=(this.page.currentPage-1)*this.page.perPage;
                   return this.problems.slice(start,start+this.page.perPage);
                },
                set:function(){

                }
            }
        },
        methods:{
            changePage:function(){

            }
        },
        ready:function(){
            $(".ui.dropdown").dropdown();
            //var  n=this.problems.length%this.page.perPage;
            //var  count=this.problems.length/this.page.perPage;
            this.page.currentPage=parseInt(this.$route.params.page);
            console.log(this.page.currentPage+1);
            //this.page.pageCount=n==0 ? this.problems.length/this.page.perPage : this.problems.length/this.page.perPage+1;
            this.page.pageCount=this.problems.length/this.page.perPage;
        },
    }
</script>