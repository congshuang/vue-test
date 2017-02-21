<template>
    <div id="text">
        这是一个测试
        <el-button type="primary" class="my-grid" @click="change">主要按钮</el-button>
        <el-button type="danger" @keyup.17="mm">主要按钮</el-button>
        <el-button type="info" icon="close">主要按钮</el-button>
        <el-button type="success" icon="edit">主要按钮</el-button>
        <el-button type="warning" icon="search">主要按钮</el-button>
         <Date></Date>
        <input type="text" v-model="msg" >

    </div>
</template>
<script>
    import Date from './Date.vue'

    export default {
        name: 'text',
        data () {
            return {
                msg: 'Welcome to Your Vue.js App'
            }
        },
        components:{
            Date
        },methods:{
                change(){
                    this.msg = "change"
                },mm(){
                    alert(1);
            }
        },
        watch:{
            msg:function () {
                alert(1);
            }
        },beforeCreate(){
            console.log("beforeCreate");
        },created(){
            console.log("Create");
        },beforeMount(){
            console.log("beforeMount");
        },mounted(){
            console.log("mounted");

        },beforeDstroy(){
            console.log('组件销毁之前');
        },
        destroyed(){
            console.log('组件销毁之后');
        }

    }
</script>
<style scoped lang="less">
     #text{
         text-align: center;
         margin-top: 300px;
     }
    @color:red;
    .height(@h){
         height:@h;
     }
     .my-grid{
     .height(50px);
         border:1px solid @color;

     }
</style>