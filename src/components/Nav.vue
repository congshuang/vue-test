<template>
	<div id="nav">
		<div class="nav">
			<ul>
		    	<!-- <li><a href="javascript:;">首页</a></li>
		    	<li><a href="javascript:;">关注</a></li>
		    	<li><a href="javascript:;">栏目</a></li> -->
		    	<router-link to='/home' tag="li" active-class="active">
		    		<a href="javascript:;">首页</a>
		    	</router-link>
		    	<router-link to='/follow' tag="li" active-class="active">
		    		<a href="javascript:;">关注</a>
		    	</router-link>
		    	<router-link to='/column' tag="li" active-class="active">
		    		<a href="javascript:;">栏目</a>
		    	</router-link>
				<router-link to='/text' tag="li" active-class="active">
					<a href="javascript:;">测试</a>
				</router-link>
				<el-button type="danger" @click="change">主要按钮</el-button>
				<input type="text" v-model="b">
		    </ul>
		</div>
	</div>
</template>
<script>
	export default{
	    data(){
	        return{
	            b:""
			}
		},props:['msg'],
		mounted(){
	        this.b=this.msg.t;
		},methods:{
		    change(){
		        this.b="change";
			}
		}
	}
</script>