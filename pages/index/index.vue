<template>
	<view class="content">
		<cv-transfer v-model="value" :data="list"></cv-transfer>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				list: [
					{
						key: '1',
						label: '备选项1',
					},
					{
						key: '2',
						label: '备选项2',
					},
					{
						key: '3',
						label: '备选项3',
					},
					{
						key: "4",
						label: '备选项4',
					},
					{
						key: "5",
						label: '备选项5',
					},
					{
						key: "6",
						label: '备选项6',
					},
					{
						key: "7",
						label: '备选项7',
					},
					{
						key: "8",
						label: '备选项8',
					},
					{
						key: "9",
						label: '备选项9',
					},
					{
						key: "10",
						label: '备选项10',
					},
					{
						key: "11",
						label: '备选项11',
					},
					{
						key: "12",
						label: '备选项12',
					},
				],
				value: ['1', '4']
			}
		},
		watch: {
			value(newValue) {
				console.log(newValue);
			}
		},
		onLoad() {

		},
		methods: {

		}
	}
</script>

<style>
	.content {
		display: flex;
		flex-direction: column;
		align-items: center;
		justify-content: center;
		padding: 20rpx;
	}
</style>
