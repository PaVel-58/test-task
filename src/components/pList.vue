<template>
	<div>
		<h3 class="list-title">Итого можете внести в качестве досрочных:</h3>
		<ul class="list">
			<li 
				v-for="(item, index) in listsItems"
				:key="index"
				class="list-item"
			>
				<pCheckbox 
					:isActive="item.active" 
					@click="item.active = !item.active"
				/>
				<span class="price">{{item.price + ' '}}</span>
				<span class="date">в {{index + 1}}-ый год</span>
			</li>
		</ul>
	</div>
</template>

<script>
	import pCheckbox from '@/components/pCheckbox' 
	export default {
		components: {
			pCheckbox
		},
		props: {
			listsItems: {
				type: Array
			}
		}
	}
</script>

<style>
	.list-title {
		font-weight: 500;
		font-size: 14px;
		line-height: 24px;
		color: #000000;
	}
	.list {
		padding: 0;
		margin: 0 0 20px;
		list-style: none;
	}
	.list-item {
		width: 100%;
		padding: 16px 0;
		border-bottom: 1px solid #DFE3E6;
	}
	.list span {
		font-weight: normal;
		font-size: 14px;
		line-height: 24px;
		color: #000000;
	}
	.price {
		margin-left: 11px;
	}
	.list span.date {
		color: #808080;
	}
</style>