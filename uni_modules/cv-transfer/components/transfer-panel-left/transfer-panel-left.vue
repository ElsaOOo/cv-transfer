<template>
	<view class="cv-transfer-panel">
		<view class="cv-transfer-panel-header">
			{{title}}
		</view>
		<view class="cv-transfer-panel-body">
			<checkbox-group @change="checkboxChange" v-if="data.length">
				<label class="cv-list-cell" v-for="item in data" :key="item.key">
					<view>
						<checkbox :value="String(item.key)" style="transform:scale(0.8)" />
					</view>
					<view class="item-label">{{item.label}}</view>
				</label>
			</checkbox-group>
			<view class="empty-data" v-else>
				无数据
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		name: 'transfer-panel',
		props: {
			data: {
				type: Array,
				default: () => ([])
			},
			title: {
				type: String,
				default: '列表1'
			}
		},
		methods: {
			checkboxChange(event) {
				this.$emit('onSelect', event.detail.value)
			}
		}
	}
</script>

<style lang="scss" scoped>
	.cv-transfer-panel {
		flex: 45%;
		border: 1px solid #ebeef5;
		border-radius: 4px;
		overflow: hidden;
		background: #fff;
		display: inline-block;
		vertical-align: middle;
		max-height: 100%;
		box-sizing: border-box;
		position: relative;

		&-header {
			height: 60rpx;
			line-height: 60rpx;
			background: #f5f7fa;
			margin: 0;
			padding-left: 15px;
			border-bottom: 1px solid #ebeef5;
			box-sizing: border-box;
			color: #000;
		}

		&-body {
			padding: 6px 0;
			min-height: 250rpx;
			height: 170px;
			overflow-y: auto;
			.empty-data {
				margin: 0;
				height: 30px;
				line-height: 30px;
				padding: 6px 15px 0;
				color: #909399;
				text-align: center;
				font-size: 14px;
			}

			.cv-list-cell {
				display: inline-flex;
				align-items: center;
			}

			.item-label {
				font-size: 14px;
			}
		}
	}
</style>
