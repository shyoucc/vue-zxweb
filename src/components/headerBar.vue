<!--

@param {String} headerTitle
  标题文本

@param {Boolean} showreturn
  是否显示返回

@slot {dom} right
  右侧自定义,不传没有

-->

<template>
	<header class="header">
		<div class="header-leftlink">
			<slot name="left">
          <span v-if="showreturn" class="icon-return" @click="$router.go(-1)"></span>
      </slot>
		</div>
		<h2 class="header-title" v-text="headerTitle"></h2>
		<div class="header-rightlink">
			<slot name="right"></slot>
		</div>
	</header>
</template>
<script>
	export default {
		name: 'header',
		props: {
			headerTitle: String,
      showreturn: {
          type: Boolean,
          default: true
      }
		}
	};
</script>
<style lang = "scss" scoped>
	.header {
	    align-items: center;
      background-color: #4773BB;
      box-sizing: border-box;
      color: #ffffff;
      display: flex;
      font-size: 18px;
      height: 40px;
      line-height: 1;
      padding: 0 10px;
      position: relative;
      text-align: center;
      white-space: nowrap;
      .header-title {
		    font-size: inherit;
        font-weight: normal;
        flex: 1;
      }
      .header-leftlink {
      	background-color: transparent;
        border: 0;
        box-shadow: none;
        color: inherit;
        display: inline-block;
        padding: 0;
        font-size: inherit;
        text-align: left;
        font-size: 24px;
      }
      .header-rightlink {
       	background-color: transparent;
        border: 0;
        box-shadow: none;
        color: inherit;
        display: inline-block;
        padding: 0;
        font-size: inherit;
        text-align: right;
      }

	}
</style>
