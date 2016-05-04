<template>

  <h1 class="ui teal image header">
      <img class="image" src="/static/img/login.png" style="width: 60px;height: 60px">
      <div class="content">
          数字化题库与试卷生成系统
      </div>
   </h1>
      <form class="ui large form">
          <div class="ui stacked segment">
             <div class="field">
                 <div class="ui left icon input">
                     <i class="user icon"></i>
                     <input type="text" placeholder="用户名" name="email">
                 </div>
             </div>

              <div class="field">
                  <div class="ui left icon input">
                      <i class="lock icon"></i>
                      <input type="text" placeholder="密码" name="password">
                  </div>
              </div>

              <div class="two wide field">
                  <div class="ui selection dropdown">
                      <i class="empty star icon"></i>
                      <input name="right" type="hidden" v-model="userType">
                      <i class="dropdown icon"></i>
                      <div class="default text">登陆身份</div>
                      <div class="menu">
                          <div v-for="role in roles" class="item" v-bind:data-value="{{role.text}}">{{role.text}}</div>
                      </div>
                  </div>
              </div>
              <div class="ui fluid large teal submit button" v-on:click="login">登陆</div>
          </div>
          <div class="ui error message"></div>
      </form>
      <div class="ui message">
          新用户? <a href="#">注册</a>
      </div>
     {{userType}}
</template>
<style>

</style>
<script>
    export default{
        data(){
            return {
                userType: "",
                roles: [
                    {text: "学生", value: "student"},
                    {text: "教师", value: "teacher"},
                    {text: "管理员", value: "admin"}
                ]
            }
        },
        components: {

        },
        methods:{
          login:function () {
              this.$dispatch("redirect",this.userType);
          }
//              var self=this;
//              if(self.userType==="学生")
//              {
//                  self.$route.router.go("/test");
//              }else if(self.userType==="教师")
//              {
//                  self.$route.router.go("/testHome");
//              }else if(self.userType==="管理员"){
//                  self.$route.router.go("/testHome");
//              }
//          }
        },
        ready: function () {
                $(".ui.selection.dropdown").dropdown();
        }
    }
</script>