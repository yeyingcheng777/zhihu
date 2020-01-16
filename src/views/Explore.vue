<template>
	<div>
		<div class="banner">
			<!-- <img src="../assets/image/heart.png" alt="" /> -->
			<i class="iconfont" style="color: rgb(0, 132, 255);">&#xe62c;</i>
			<h4 style="margin-left: 20px;">全部专题</h4>
			<h5 style="margin-left: 20px; color: rgb(133, 144, 166);">共有{{specials.length}}个专题</h5>
		</div>
		<div class="container">
			<div class="row" v-for="(item, index) in specials" :key="index">
				<div class="col-4"><img :src="item.banner" alt="" /></div>

				<div class="col-8">
					<h4>{{ item.title }}</h4>
					<p class="meta">{{item.updated | changeTime }} 更新，{{ item.viewCount }}次浏览</p>
					<p class="introduction">{{ item.introduction }}</p>
					<span v-for="(section, index) in item.sections" :key="index" class="section">
					{{ section.sectionTitle }}
					</span>
				</div>
			</div>
		</div>
	</div>
</template>
<script>
	
export default {
	name: 'special',
	data() {
		return {
			specials: [],
			page: 0,
			onFetching: false
		};
	},
	created() {
		this.axios.get('http://localhost:8080/api/special').then(res =>{
			console.log(res.data.data.length);
			this.specials = res.data.data;
		});
		
	},
	// methods: {
	// 	filters: {
	// 		 //timeago.js插件
	// 		    //计算时间，类似于几分钟前，几小时前，几天前等
	// 		    changeTime(val){
	// 		        let time = new Date(val); //先将接收到的json格式的日期数据转换成可用的js对象日期
	// 		        return new timeago().format(time, 'zh_CN'); //转换成类似于几天前的格式
	// 		    }
			
			
	     
	}
	},
	
	
	
};
</script>
<style lang="scss" scoped>
	@font-face {
	  font-family: 'iconfont';  /* project id 1434147 */
	  src: url('//at.alicdn.com/t/font_1434147_ugaee38lw.eot');
	  src: url('//at.alicdn.com/t/font_1434147_ugaee38lw.eot?#iefix') format('embedded-opentype'),
	  url('//at.alicdn.com/t/font_1434147_ugaee38lw.woff2') format('woff2'),
	  url('//at.alicdn.com/t/font_1434147_ugaee38lw.woff') format('woff'),
	  url('//at.alicdn.com/t/font_1434147_ugaee38lw.ttf') format('truetype'),
	  url('//at.alicdn.com/t/font_1434147_ugaee38lw.svg#iconfont') format('svg');
	}
	.iconfont{
	    font-family:"iconfont" !important;
	    font-size:30px;font-style:normal;
	    -webkit-font-smoothing: antialiased;
	    -webkit-text-stroke-width: 0.2px;
	    -moz-osx-font-smoothing: grayscale;}

h4 {
	color: rgb(39, 40, 34);
	font-size: 20px;
}
.banner {
	width: 90%;
	margin-bottom: 10px;
	margin-top: 80px;
	height: 100px;
	border: 1px solid #d6d6d6;
	box-shadow: 2px 5px 5px #ddd;
	padding-left: 10%;
	display: flex;
	align-items: center;

}
.container {
	display: block;
	width: 1000px;
	margin: 10px auto 0;
	
	.row {
		background-color: rgb(39, 40, 34);
		// background-color: #ffffff;
		display:flex ;
		border: 1px solid #d6d6d6;
		border-radius: 4px;
		height: 100000%;
		padding: 24px;
		box-shadow: 0 1px 3px 0 rgba(26, 26, 26, 0.1);
		.col-4 {
			flex: 0 0 33%;
			height: auto;
			img {
				width: 100%;
				height: 100%;
				border-radius: 10px;
			}
		}
		.col-8 {
			margin-left: 30px;
		}
	}
}
.introduction {
	font-size: 20px;
	color: #5c5e5c;
}
</style>