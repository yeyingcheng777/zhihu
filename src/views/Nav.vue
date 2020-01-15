<template>
	<div>
		<div class="nav gutter">
			<div class="nav-bar">
				<!-- <ul class="nav-list">
					<li class="nav-item"><router-link to="/home">首页</router-link></li>
				    <li class="nav-item"><router-link to="/explore">发现</router-link></li>
					<li class="nav-item"><router-link to="/question/waiting">等你来答</router-link></li>
					<li class="nav-item abs-center-right"><router-link to="/login">登录</router-link></li>
				</ul><div class="line"></div> -->
<el-menu :default-active="activeIndex2"
  class="el-menu-demo"
  mode="horizontal"
  background-color="#545c64"
  text-color="#fff"
  active-text-color="#ffd04b">
  <el-menu-item index="1" style="font-size: larger;"><router-link to="/home">首页</router-link></el-menu-item>
  <el-menu-item index="2" style="font-size: larger;"><router-link to="/explore">发现</router-link></el-menu-item>
  <el-menu-item index="3" style="font-size: larger;"><router-link to="/question/waiting">等你来答</router-link></el-menu-item>
  <el-menu-item index="4" style="font-size: larger;"><router-link to="/login">登录</router-link></el-menu-item>
  <el-menu-item index="5" style="font-size: larger;"><router-link to="/special/all">查看全部</router-link></el-menu-item>
</el-menu>

			</div>
		</div>
		<!-- 二级路由入口 -->
		<router-view />
	</div>
</template>

<script>
	export default {
		name: 'nav',
		data() {
			return {};
		},
		created() {}
	}
</script>

<style lang="scss" scoped>
	// .router-link-active{
	// 	border-bottom: 2px solid #000000;
	// }
// 	.nav-bar{
// 		background-color: #000000;
// 	}
// 	.gutter{
// 		position: relative;
// 		margin-bottom: 10px;
// 	}
// 	​
// 	ul {
// 	    list-style-type: none;
// 	    margin: 0;
// 	    padding: 0;
// 	    overflow: hidden;
// 	    background-color: #55aaff;
// 	}
	
// 	li {
// 	    float: left;
// 	}

// li a {
//     display: block;
//     color: black;
//     text-align: center;
//     padding: 14px 16px;
//     text-decoration: none;
// }

// li a:hover:not(.active) {
//     background-color: #ed5564;
// }

// .active {
//     background-color: #4CAF50;
// }
</style>
