<template>
    <div class="ui middle aligned center aligned grid">
        <div class="row">
        <!--<div class="two wide column" style="text-align: center">-->
            <!--<div class="direct"><i class="long arrow left icon"><a ></a></i></div>-->
        <!--</div>-->
        <div class="twelve wide column " style="text-align: left">
            <div class="question">
                <template v-for="question in questions">
                <div class="ui form" style="margin-top: 6px;">
                    <label class="question_des" for="choice">{{$index+1}}.&nbsp;{{question.label}}</label>
                    <div class="field">
                        <div class="ui radio checkbox">
                            <input class="hidden" tabindex="0" name="choice" type="radio">
                            <label>{{question.choiceOne}}</label>
                        </div>
                    </div>
                    <div class="field">
                        <div class="ui radio checkbox">
                            <input class="hidden" tabindex="0" name="choice" type="radio">
                            <label>{{question.choiceTwo}}</label>
                        </div>
                    </div>
                    <div class="field">
                        <div class="ui radio checkbox">
                            <input class="hidden" tabindex="0" name="choice" type="radio">
                            <label>{{question.choiceThree}}</label>
                        </div>
                    </div>
                    <div class="field">
                        <div class="ui radio checkbox">
                            <input class="hidden" tabindex="0" name="choice" type="radio">
                            <label>{{question.choiceFour}}</label>
                        </div>
                    </div>
                </div>
              </template>
            </div>
            <div style="text-align: right">
            <button class="ui teal button" type="button" >下一页</button>
             </div>
        </div>
        <!--<div class="two wide column" style="text-align: center">-->
            <!--<div class="direct"><i class="long arrow right icon"><a></a></i></i></div>-->
        <!--</div>-->
        </div>
     </div>
</template>
<style>
    .two.wide.column .direct{
        border: 1px solid lightgray;
        background-color: lightgray;
        border-radius: 2px;
        height:36px;
        padding-top: 8px;
        padding-bottom: 8px;
    }
    .twelve.wide.column .question{
        border:1px solid lightgrey;
        /*height: 400px;*/
        border-radius: 8px;
        padding-top:24px;
        padding-left:24px;
        padding-bottom: 24px;
        background-color: floralwhite;
    }
    .twelve.wide.column .order{
        letter-spacing: 2px;
        margin-top: 6px;
    }
    .twelve.wide.column .question_des{
        font-size: 18px;
        letter-spacing: inherit;
        line-height: 2em;
    }
    .twelve.wide.column .question .field label{
        font-size: 16px;
    }
</style>
<script>
    export default{
        data(){
            return{
                questions:[
                    {
                        label:"不属于Ｉ／Ｏ控制方式的是:",
                        choiceOne:"查询方式",
                        choiceTwo:"重定位方式",
                        choiceThree:"DMA方式",
                        choiceFour:"中断驱动方式"
                    },
                    {
                        label:"下列特性中，哪一个不是进程的特性:",
                        choiceOne:"并发性",
                        choiceTwo:"异步型",
                        choiceThree:"静态性",
                        choiceFour:"动态性"
                    },
                    {
                        label:"产生死锁的必要条件不包括:",
                        choiceOne:"不剥夺",
                        choiceTwo:"互斥",
                        choiceThree:"请求与保持",
                        choiceFour:"非环路等待"
                    },
                    {
                        label:"页面置换算法是在（）时被调用:",
                        choiceOne:"所需页面不存在",
                        choiceTwo:"内存中无空闲物理块",
                        choiceThree:"产生地址越界中断",
                        choiceFour:"产生缺页中断"
                    }

                ]
            }
        },
        components: {

        },
        ready:function(){
            $(".ui.radio.checkbox").checkbox();
        }
    }
</script>