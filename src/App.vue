<template>
	<div id="app">
		<loading v-show="loading"></loading>
		<NavView v-show="headerShow" :msg="a"></NavView>
		<transition enter-active-class="animated zoomInLeft" leave-active-class="animated zoomOutRight">
			<keep-alive>
				<router-view class="router-view"></router-view>
			</keep-alive>
		</transition>
		{{a}}{{a}}
		<FooterView></FooterView>

	</div>
</template>
<script>
	import NavView from './components/Nav.vue'
	import FooterView from './components/Footer.vue'

	import {mapGetters, matpActions} from 'vuex'

	export default{
	    data(){
	        return{
	            a:{
	                t:"这是主组件"
				}
			}
		},
		computed:mapGetters([
			'headerShow',
			'loading',
			'test'
		]),
		watch:{
			$route(to,from){
				if(to.path=='/user-info'){
					this.$store.dispatch('hideHeader');
					this.$store.dispatch('testHeader');
				}else{
					this.$store.dispatch('showHeader');
				}
			},
			a:function () {
				alert(3);
            }
		},
		components:{
			NavView,
			FooterView
		}
	}
</script>
<style>
	@import './assets/css/index.css';
	.slide-down-enter-active,
	.slide-down-leave-active{
		transition: .4s all ease;
		opacity:0.2;
		transform: translate3d(0,6em,0);
	}
	.slide-down-enter,
	.slide-down-leave{
		opacity:1;
		transform: translate3d(0,6em,0);
	}
</style>