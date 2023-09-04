<template>
	<swiper class="banner" indicator-dots circular autoplay>
		<swiper-item v-for="item in pictures" :key="item.id">
			<image :src="item.url" @tap="onPreviewImage(item.url)"></image>
		</swiper-item>
	</swiper>
</template>

<script>
	export default {
		data() {
			return {
				title: 'Hello',
				pictures: [
					{
						id: '1',
						url: 'https://pcapi-xiaotuxian-front-devtest.itheima.net/miniapp/uploads/goods_preview_1.jpg'
					},{
						id: '2',
						url: 'https://pcapi-xiaotuxian-front-devtest.itheima.net/miniapp/uploads/goods_preview_2.jpg'
					},{
						id: '3',
						url: 'https://pcapi-xiaotuxian-front-devtest.itheima.net/miniapp/uploads/goods_preview_3.jpg'
					},{
						id: '4',
						url: 'https://pcapi-xiaotuxian-front-devtest.itheima.net/miniapp/uploads/goods_preview_4.jpg'
					},{
						id: '5',
						url: 'https://pcapi-xiaotuxian-front-devtest.itheima.net/miniapp/uploads/goods_preview_5.jpg'
					},
				]
			}
		},
		onLoad() {

		},
		methods: {
		  onPreviewImage(url) {
			  uni.previewImage({
				  urls: this.pictures.map(v => v.url),
				  current: url
			  })
		  } 
		}
	}
</script>

<style lang="scss" scoped>
 .banner {
	 width: 750rpx;
	 height: 750rpx;
	 image {
		 width: 100%;
		 height: 100%;
	 }
 }
</style>
