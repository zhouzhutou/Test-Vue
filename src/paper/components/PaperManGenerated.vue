<template>
<man-nav nav-item="试卷手动生成">
</man-nav>
<form class="ui form">
    <h4 class="ui horizontal divider header">题库试卷列表</h4>
    <search-component></search-component>


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
        </tr></thead>
    <tbody>
    <tr v-for="problem in problems">
        <td>{{problem.id}}</td>
        <td>{{problem.name}}</td>
        <td>{{problem.subject}}</td>
        <td>{{problem.type}}</td>
        <td>{{problem.knowledgePoints}}</td>
        <td>{{problem.difficulty}}</td>
        <td>{{problem.answer}}</td>
        <td>
            <button class="ui teal button">添加到试卷</button>
            <button class="ui teal button">查看</button>
        </td>
    </tr>
    <tr>
        <td>3</td>
        <td>1+1=?</td>
        <td>微积分</td>
        <td>判断题</td>
        <td>导数</td>
        <td>0.1</td>
        <td>正确</td>
        <td>
            <button class="ui teal button">添加到试卷</button>
            <button class="ui teal button">查看</button>
        </td>
    </tr>
    <tr>
        <td>4</td>
        <td>1+1=?</td>
        <td>微积分</td>
        <td>判断题</td>
        <td>导数</td>
        <td>0.4</td>
        <td>Ｂ</td>
        <td>
            <button class="ui teal button">添加到试卷</button>
            <button class="ui teal button">查看</button>
        </td>
    </tr>
    </tbody>
    </table>
    <pagination-com></pagination-com>

    <h4 class="ui horizontal divider header">试卷表</h4>

    <div class="six wide field">
        <label>试卷名称</label>
        <input type="text" placeholder="试卷名称">
    </div>
　　<div class="field">
        <table class="ui blue table">
            <thead>
            <tr>
                <th>题型</th>
                <th>题目</th>
                <th>选项A</th>
                <th>选项B</th>
                <th>选项C</th>
                <th>选项D</th>
                <th>答案</th>
                <th>操作</th>
            </tr>
            </thead>
            <tbody>
            <tr v-for="selected in selecteds">
               <td>
                   {{selected.type}}
               </td>
               <td>
                   {{selected.name}}
               </td>
               <td>
                   {{selected.a}}
               </td>
               <td>
                   {{selected.b}}
               </td>
               <td>
                   {{selected.c}}
               </td>
               <td>
                   {{selected.d}}
               </td>
               <td>
                   {{selected.answer}}
               </td>
               <td>
                   <button class="ui teal button">编辑</button>
               </td>
            </tr>
            <tr style="font-weight: bold">
                <td>
                    当前总分
                </td>
                <td>
                    20
                </td>
            </tr>
            </tbody>
        </table>
    </div>
    <button class="ui teal button">浏览试卷</button>
    <button class="ui teal button">确认生成</button>
</form>
</template>
<style>
    .ui.blue.table{
        margin-top: 0px;
        padding: 0px;
    }
    .ui.teal.button{
        margin-right:12px;
    }
</style>
<script>
    var manNav=require("../../common/Nav.vue");
    var searchComponent=require("../../common/Search.vue");
    var paginationCom=require("../../common/Pagination.vue")
    export default{
        data(){
            return{
                problems:[{
                    id:1,
                    name:"1+1=?",
                    subject:"微积分",
                    type:"选择题",
                    knowledgePoints:"傅里叶",
            　　　　　difficulty:0.3,
                    answer:"A"　
                },
                    {
                        id:2,
                        name:"1+1=?",
                        subject:"微积分",
                        type:"选择题",
                        knowledgePoints:"多元微分",
                        difficulty:0.2,
                        answer:"B"
                    }
                ],
                selecteds:[
                    {
                        type:"选择题",
                        name:"1+1=?",
                        a:"1",
                        b:"2",
                        c:"3",
                        d:"4",
                        answer:"B"
                    },
                    {
                        type:"选择题",
                        name:"1+1=?",
                        a:"1",
                        b:"2",
                        c:"3",
                        d:"4",
                        answer:"B"
                    },
                    {
                        type:"选择题",
                        name:"1+1=?",
                        a:"1",
                        b:"2",
                        c:"3",
                        d:"4",
                        answer:"B"
                    }
                ]
            }

        },
        components:{
        manNav:manNav,
        searchComponent:searchComponent,
        paginationCom:paginationCom
        },
        ready:function () {

        }
    }
</script>