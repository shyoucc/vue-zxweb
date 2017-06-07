<!--

@param {String} backcolor
	success	绿色
    danger  红色

@param {Boolean} disabled
	禁用按钮

@param {String} size
	normal 中尺寸
	small 小尺寸

@slot 传入按钮文本

-->

<template>
	<div class="button">
		<button class="button"
		:class="[{
			'button-disabled': disabled,
			'button-success': backcolor === 'success',
			'button-danger': backcolor === 'danger',
			'button-normal': size === 'normal',
			'button-small': size === 'small'
		}]"
		:disabled="disabled"
		@click="handleClick()">
		<span><slot>确定</slot></span>
		</button>
	</div>
</template>
<script>
	export default {
		props: {
			disabled: Boolean,
			backcolor: {
				type: String,
				default: ''
			},
			size: {
				type: String,
				default: ''
			}
		},
		methods: {
			handleClick(e){
				this.$emit('click', e);
			}
		}
	};
</script>
<style lang='scss' scoped>
	@import "../common/css/let";

	.button {
	    display: flex;
	    justify-content: center;
		.button {
			border-radius: 4px;
			border: 0;
			box-sizing: border-box;
			color: inherit;
			display: block;
			font-size: 18px;
			height: 41px;
			outline: 0;
			overflow: hidden;
			text-align: center;
			position: relative;
		    background-color: $buttonDefault;
		    color: #ffffff;
		    width: 90%;
		    &:active {
				opacity: .9;
		    }
		}
		.button-success {
			background-color: $buttonSuccess;
		}
		.button-danger {
			background-color: $buttonDanger;
		}
		.button-disabled {
			opacity: .5;
		}
		.button-normal {
			display: inline-block;
			padding: 0 15px;
			width: inherit;
		}
		.button-small {
			display: inline-block;
	        font-size: 14px;
	        padding: 0 12px;
	        height: 30px;
	        width: inherit;
		}
	}
</style>