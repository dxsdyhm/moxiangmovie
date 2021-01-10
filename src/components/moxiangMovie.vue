<template>
	<b-container class="pb-5">
		<video-player class="video-player vjs-custom-skin" ref="videoPlayer" :playsinline="true" :options="playerOptions"></video-player>
		<b-input-group prepend="地址" class="mt-3">
			<b-form-input v-model="userinput" placeholder="粘贴影视地址" type="url"></b-form-input>
			<b-input-group-append>
				<b-button variant="info" @click="plaSrc(userinput)">播放</b-button>
			</b-input-group-append>
		</b-input-group>
		<b-row class="mt-2 ml-1">
			<b-button @click='quickstar(item)' variant="outline-primary" class="m-1" v-for="item in likes" :key="item.name">
			    {{ item.name }}
			  </b-button>
		</b-row>
	</b-container>
</template>

<script>
	export default {
		data() {
			return {
				userinput:'',
				playerOptions: {
					playbackRates: [0.7, 1.0, 1.5, 2.0], //播放速度
					autoplay: true, //如果true,浏览器准备好时开始回放。
					muted: false, // 默认情况下将会消除任何音频。
					loop: false, // 导致视频一结束就重新开始。
					preload: 'auto', // 建议浏览器在<video>加载元素后是否应该开始下载视频数据。auto浏览器选择最佳行为,立即开始加载视频（如果浏览器支持）
					language: 'zh-CN',
					aspectRatio: '16:9', // 将播放器置于流畅模式，并在计算播放器的动态大小时使用该值。值应该代表一个比例 - 用冒号分隔的两个数字（例如"16:9"或"4:3"）
					fluid: true, // 当true时，Video.js player将拥有流体大小。换句话说，它将按比例缩放以适应其容器。
					sources: [{
						type: "application/x-mpegURL",
						src: "https://www.hyxrzs.com/20210101/tH8UDXS2/index.m3u8" //你的m3u8地址（必填）
					}],
					poster: "poster.jpg", //你的封面地址
					width: document.documentElement.clientWidth,
					notSupportedMessage: '此视频暂无法播放，请稍后再试',
				},
				likes:[
					{
						name:'我和我的家乡',
						src:'https://www.hyxrzs.com/20210101/tH8UDXS2/index.m3u8'
					},
					{
						name:'粽邪2',
						src:'https://good.jieshuo-okzy.com/20201231/9023_825a9355/index.m3u8'
					},
					{
						name:'CCTV-1综合',
						src:'http://ivi.bupt.edu.cn/hls/cctv1hd.m3u8'
					},
					{
						name:'CCTV-6电影',
						src:'http://ivi.bupt.edu.cn/hls/cctv6hd.m3u8'
					},
					{
						name:'CCTV-13新闻',
						src:'http://ivi.bupt.edu.cn/hls/cctv13hd.m3u8'
					},
					{
						name:'湖南卫视',
						src:'http://ivi.bupt.edu.cn/hls/hunanhd.m3u8'
					},
					{
						name:'7号房的礼物',
						src:'https://yushou.qitu-zuida.com/20180225/jlVaEdK9/index.m3u8'
					},
					{
						name:'疯狂的石头',
						src:'http://yi.jingdianzuida.com/20190908/cPbNPkEn/index.m3u8'
					}
				]
			}
		},
		methods:{
			quickstar:function(movie){
				this.plaSrc(movie.src)
			},
			plaSrc:function(url){
				let myPlayer = this.$refs.videoPlayer.player;
				myPlayer.src(url);
			}
		}
	}
</script>

<style>
</style>
