# cv-transfer 穿梭框
> **组件名：cv-transfer**



 Transfer 穿梭框

### 安装方式

本组件符合[easycom](https://uniapp.dcloud.io/collocation/pages?id=easycom)规范，`HBuilderX 2.5.5`起，只需将本组件导入项目，在页面`template`中即可直接使用，无需在页面中`import`和注册`components`。

> **注意事项**

> 为了避免错误使用，给大家带来不好的开发体验，请在使用组件前仔细阅读下面的注意事项，可以帮你避免一些错误。

### 基本用法

在 ``template`` 中使用组件

```html
<!-- 一般用法 -->
<view class="content">
  <cv-transfer v-model="value" :data="list"></cv-transfer>
</view>
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
					},1111111
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
```



穿梭框组件和element-ui 中的穿梭框组件使用方式基本一致

## API

### Transfer Props

| 属性名      | 说明                                     | 类型                  | 默认值               |
| ----------- | ---------------------------------------- | --------------------- | -------------------- |
| value       | 绑定值，字符串数组                       | array                 | []                   |
| data        | Transfer 的数据源，key一定要为字符串类型 | array[{ key, label }] | []                   |
| titles      | 自定义列表标题                           | array                 | ['列表 1', '列表 2'] |
| buttonTexts | 自定义按钮文案                           | array                 | [ '<', '>']          |

​	

欢迎报bug，提改进。