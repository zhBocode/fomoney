<template>
  <!--banner-->
	<div>
		<div class="en-banner"><img src="/static/images/en_banner.jpg" alt="走进汇智星banner" /></div>
	<!--nav-->
	<div class="enter-fosun">
		<ul class="nav wc1200 clearfix">
			<li v-for="item in data">
				<a href="javascript:;"  @click="goUrl(item)">{{item.label}}<span :class="{active:item.isA}"></span></a>
			</li>
		</ul>
	</div>
	<router-view></router-view>
</div>
  
</template>

<script>

export default {
	data(){
		 return{
			data:[
				{
					label:'公司介绍',
					url:'/enIndex/aboutUs',
					isA:false
				},
				{
					label:'新闻中心',
					url:'/enIndex/newsCenter',
					isA:false
				},
				{
					label:'领导团队',
					url:'/enIndex/leadershipTeam',
					isA:false
				},
				{
					label:'发展历程',
					url:'/enIndex/developmentHistory',
					isA:false
				},
				{
					label:'品牌文化',
					url:'/enIndex/brandCulture',
					isA:false
				},
				{
					label:'合作伙伴',
					url:'/enIndex/cooperativePartner',
					isA:false
				}
			]
		 }
	 },
	 methods:{
		 goUrl(obj){
			this.$router.push({ path: obj.url })
			this.data.map(function (v,i) {
				v.url==obj.url?v.isA=true:v.isA=false;
			});
		 }
	 },
	 created(){
		 const _path = this.$route.path;
		 this.data.map(function (v,i) {
			v.url==_path?v.isA=true:v.isA=false;
		 });
	 }
}

</script>
