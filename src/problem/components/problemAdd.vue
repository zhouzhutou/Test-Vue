<template>
  <add-nav nav-item="试题添加"></add-nav>
    <div>
    <form class="ui form">
        <h4 class="ui  header">试题添加</h4>
        <div class="field">
            <div class="six wide field">
                <label>题目名称</label>
                <input name="questionName" placeholder="题目名称" type="text">
            </div>
        </div>

        <div class="field">
        <div class="two wide field">
            <!--<div class="two wide field">-->
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
            <!--</div>-->
        </div>
        </div>

        <div class="field">
        <div class="two wide field">
            <!--<div class="two wide field">-->
            <label>题型</label>
            <div class="ui selection dropdown">
                <div class="default text">题型</div>
                <i class="dropdown icon"></i>
                <input name="problemType" type="hidden" v-model="type">
                <div class="menu" >
                   <template v-for="problemType in problemTypes">
                       <div class="item" :data-value="{{problemType.type}}">{{problemType.type}}</div>
                   </template>
                </div>
            </div>
         </div>
            <!--</div>-->
        </div>

        <div class="field">
        <div class="two wide field">
            <!--<div class="two wide field">-->
            <label>难度</label>
            <div class="ui selection dropdown">
                <div class="default text">难度</div>
                <i class="dropdown icon"></i>
                <input name="problemType" type="hidden">
                <div class="menu">
                    <div class="item" data-value="1">0.1</div>
                    <div class="item" data-value="2">0.2</div>
                    <div class="item" data-value="3">0.3</div>
                    <div class="item" data-value="4">0.4</div>
                    <div class="item" data-value="5">0.5</div>
                </div>
            </div>
            <!--</div>-->
        </div>
        </div>
        <!--</div>-->

        <div>
        <div class="answer">
        <div class="grouped fields">
            <label for="answer-1">选择题答案:</label>
            <div class="field">
                <div class="ui radio checkbox">
                    <input class="hidden"  name="answer-1" checked="checked" type="radio">
                    <label>A</label>
                </div>
            </div>
            <div class="field">
                <div class="ui radio checkbox">
                    <input class="hidden"  name="answer-1" type="radio">
                    <label>B</label>
                </div>
            </div>
            <div class="field">
                <div class="ui radio checkbox">
                    <input class="hidden"  name="answer-1" type="radio">
                    <label>C</label>
                </div>
            </div>
            <div class="field">
                <div class="ui radio checkbox">
                    <input class="hidden"  name="answer-1" type="radio">
                    <label>D</label>
                </div>
            </div>
        </div>
        </div>

        <div class="answer">
        <div class="grouped fields">
            <label for="answer">判断题答案:</label>
            <div class="field">
                <div class="ui radio checkbox">
                    <input class="hidden"  name="answer-2" checked="checked" type="radio">
                    <label><i class="checkmark icon"></i></label>
                </div>
            </div>
            <div class="field">
                <div class="ui radio checkbox">
                    <input class="hidden"  name="answer-2" type="radio">
                    <label><i class="remove icon"></i></label>
                </div>
            </div>
         </div>
         </div>

        <div class="answer">
        <div>
            <div class="six wide field">
                <label>论述题答案</label>
                <textarea style=""></textarea>
            </div>
        </div>
         </div>
       </div>
        <button class="ui teal button" type="submit">添加</button>
    </form>
    </div>
</template>
<style>
    .ui.form{
        margin-top: 14px;
    }
    .ui.teal.button{
        margin-top: 12px;
    }
</style>
<script>
   var addNav=require("./../../common/Nav.vue");
    export default{
        data(){
            return{
                type:"",
                choices:[],
                problemTypes:[
                    {type:'选择题'},
                    {type:'判断题'},
                    {type:'论述题'}
                ]
            }
        },
        watch:
        {
           'type':function(val,oldVal){
               console.log('new: %s, old: %s', val, oldVal);
               this.$emit('changed',val);
//               var i;
//               if(val==="选择题") {
//                   this.choices[0] = val;
//                   for ( i = 0; i < this.choices.length; i++) {
//                       if (i != 0) {
//                           this.choices[i] = "";
//                       }
//                   }
//               }
//               else if(val==="判断题") {
//                   this.choices[1] = val;
//                   for ( i = 0; i < this.choices.length; i++) {
//                       if (i != 1) {
//                           this.choices[i] = "";
//                       }
//                   }
//
//               }
//               else if(val==="论述题")
//               {
//                   this.choices[2] = val;
//                   for ( i = 0; i < this.choices.length; i++) {
//                       if (i != 2) {
//                           this.choices[i] = "";
//                       }
//                   }
//               }
               console.log(this.choices);
           }
        },
        components:{
            addNav:addNav
        },
        ready:function () {
            $(".answer").hide();
            $(".ui.selection.dropdown").dropdown();
            $(".ui.radio.checkbox").checkbox();
            this.$on("changed",function(val){
                if(val=="选择题")
                {
                    var selected=$(".answer").eq(0);
                    selected.show();
                    selected.siblings().hide();

                }else if(val=="判断题"){
                    var selected=$(".answer").eq(1);
                    selected.show();
                    selected.siblings().hide();
                }else if(val=="论述题"){
                    var selected=$(".answer").eq(2);
                    selected.show();
                    selected.siblings().hide();
                }
            });
        }

    }
</script>