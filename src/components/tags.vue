<template>
	<div class="tags-view">
		<span class="tags-label">{{label}}</span>
		<pTag 
			class="tags-item"
			v-for="(item, index) in tagsItem"
			:key="index"
			:text="item.name" 
			:isActive="item.active"
			@click="item.active = !item.active"
		/>
	</div>
</template>

<script>
	import pTag from '@/components/pTag'
	export default {
		props: {
			tagsItem: Array,
			label: String
		},
		components: {
			pTag
		},
		// computed() {
		// 	activeTag(value) {

		// 	}
		// }
	}	
</script>

<style>
	.tags-label {
		font-weight: 500;
		font-size: 14px;
		line-height: 24px;
		color: #000000;
		margin-right: 32px;
	}
	.tags-item {
		margin-right: 16px;
	}
	.tags-item:last-child {
		margin-right: 0;
	}
	@media only screen and (max-width: 320px) {
		.tags-label {
			display: block;
			margin-bottom: 24px;
		}
	}
</style>