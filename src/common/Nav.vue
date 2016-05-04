<template>
    <div class="nav">
        <div class="ui large breadcrumb">
            <a class="section" style="color: lightgrey">首页</a>
            <i class="right chevron icon divider"></i>
            <div class="active section">{{navItem}}</div>
        </div>
    </div>
    <div class="ui clearing divider"></div>
</template>
<style>
    .nav {
        padding-top: 6px;
        font-size: 16px;
        font-family: 'Lato', 'Helvetica Neue', Arial, Helvetica, sans-serif;
        color: lightgrey;
    }
    .ui.clearing.divider{
        margin-top: 6px;
    }
</style>
<script>

    export default{
        data(){
            return{
                msg:'hello vue'
            }
        },
        props:['navItem'],
        components:{

        }
    }
</script>