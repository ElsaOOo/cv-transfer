<template>
	<view class="cv-transfer">
		<transfer-panel-left :data="unSelectData" :title="titles[0]" @onSelect="onSelect"></transfer-panel-left>
		<view class="cv-transfer-btns">
			<button type="default" size="mini" :disabled="undoBtnDisabled" @click="doUnSelect">{{buttonTexts[0]}}</button>
			<button type="default" size="mini" :disabled="doSelectBtnDisabled" @click="doSelect">{{buttonTexts[1]}}</button>
		</view>
		<transfer-panel-right :data="selectedData" :title="titles[1]" @onUnSelect="onUnSelect"></transfer-panel-right>
	</view>
</template>
<script>
	export default {
		name: 'cv-transfer',
		model: {
			prop: 'value',
			event: 'change'
		},
		props: {
			// 选中的数据
			value: {
				type: Array,
				default: () => ([])
			},
			// 源数据
			data: {
				type: Array,
				default: () => ([])
			},
			// 自定义列表标题
			titles: {
				type: Array,
				default: () => (['列表1', '列表2'])
			},
			// 自定义按钮文案
			buttonTexts: {
				type: Array,
				default: () => (['<', '>'])
			}
		},
		data() {
			return {
				undoBtnDisabled: true,
				doSelectBtnDisabled: true,
				doSelectValues: [],
				undoSelectValues: []
			}
		},
		computed: {
			unSelectData() {
				const value = this.data.filter((item) => !this.value.includes(item.key))
				return value
			},
			selectedData() {
				const value = this.data.filter((item) => this.value.includes(item.key))
				return value
			}
		},
		methods: {
			// 左侧选中
			onSelect(value) {
				this.doSelectBtnDisabled = false;
				this.doSelectValues = value;
			},
			// 右侧取消选中
			onUnSelect(value) {
				this.undoBtnDisabled = false;
				this.undoSelectValues = value;
			},
			doSelect() {
				this.$emit('change', [...new Set([...this.value, ...this.doSelectValues])]);
				this.doSelectBtnDisabled = true;
				this.doSelectValues = [];
			},
			doUnSelect() {
				this.$emit('change', this.value.filter((item) => !this.undoSelectValues.includes(item)));
				this.undoBtnDisabled = true;
				this.undoSelectValues = [];
			}
			
		}
	}
</script>
<style lang="scss" scoped>
	.cv-transfer {
		display: flex;
		justify-content: space-between;
		align-items: center;
		width: 100%;

		.cv-transfer-btns {
			text-align: center;
		}
	}
</style>
