<template>
  <div class="index">
  	 <zx-header header-title="首页"></zx-header>
  	 <div class="content">
	      从这里开始>>>
  	 </div>
  </div>
</template>
<script>
	import zxHeader from '@/components/headerBar';
	export default {
		name: 'index',
		components: {
			zxHeader
		}
	};
</script>
<style lang="scss" scoped>
	.index {
		.content {
			padding: 20px;
		}
	}
</style>
