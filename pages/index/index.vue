<template>
	<view class="container">
		<button @click="selectPhoto">获取照片</button>
		<image :src="imagefile"></image>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				imageUrl: '',
				imagefile: '',
			}
		},
		methods: {
			selectPhoto() {
				uni.chooseImage({
					count: 1,
					success: (res) => {
						console.log(res)
						this.imagefile = res.tempFilePaths[0]
					}
				})
			}
		}
	}
</script>

<style>
	.container {
		padding: 20px;
		font-size: 14px;
		line-height: 24px;
	}
</style>
