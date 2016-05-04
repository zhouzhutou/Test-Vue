<template>
　　<user-nav nav-item="用户列表"></user-nav>
   <div class="ui form">
       <div class="fields">
           <div class="three wide field">

               <input name="number" maxlength="16" placeholder="用户编号" type="text">
           </div>
           <div class="three wide field">

               <input name="name" maxlength="3" placeholder="用户姓名" type="text">
           </div>
           <div class="two wide field">

                <select class="ui fluid search dropdown" >
                           <option value="学生">学生</option>
                           <option value="教师">教师</option>
                </select>
            </div>
            <div class="field">
                <label>  </label>
                <button class="ui grey button"> <i class="search icon"></i>搜索</button>
            </div>

      </div>
       </div>
    <table class="ui celled table">
        <thead>
        <tr><th>用户编号</th>
            <th>用户姓名</th>
            <th>用户类型</th>
            <th>操作</th>
        </tr></thead>
        <tbody>
        <tr>
            <td>
                201521060439
            </td>
            <td> shepherd</td>
            <td> 学生</td>
            <td>
                <button class="ui teal button">查看信息</button>
                <button class="ui teal button">删除用户</button>
            </td>
        </tr>
        <tr>
            <td>201521060440</td>
            <td>李四</td>
            <td>学生</td>
            <td>
                <button class="ui teal button">查看信息</button>
                <button class="ui teal button">删除用户</button>
            </td>
        </tr>
        <tr>
            <td>20152106044１</td>
            <td>小红</td>
            <td>学生</td>
            <td>
                <button class="ui teal button">查看信息</button>
                <button class="ui teal button">删除用户</button>
            </td>
        </tr>

        </tbody>
        <tfoot>
        <tr>
            <th>
                <button class="ui basic button"><i class="add user icon"></i> 添加用户</button>
            </th>
            <th colspan="3">
            <div class="ui right floated pagination menu">
                <a class="icon item">
                    <i class="left chevron icon"></i>
                </a>
                <a class="item">1</a>
                <a class="item">2</a>
                <a class="item">3</a>
                <a class="item">4</a>
                <a class="icon item">
                    <i class="right chevron icon"></i>
                </a>
            </div>
            </th>
        </tr></tfoot>
    </table>
    </div>
</template>
<style>
.addUserButton{
    margin: 0px;
    padding: 0px;
}
 .ui.form .fields{
     margin-top: 14px;
 }
 .ui.form .fields .field{
     margin-right: 10px;
 }
</style>
<script>
    var userNav=require("../../common/Nav.vue");
    export default{
        data(){
            return{
                msg:'hello vue'
            }
        },
        components:{
            userNav:userNav
        }
    }
</script>