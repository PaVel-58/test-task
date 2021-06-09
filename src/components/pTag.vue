<template>
	<button class="tag" :isActive="isActive">
		<span 
			class="tag-price"
			v-if="price"
		>
			{{price + ' '}}
		</span>
		{{text}}
	</button>
</template>

<script>
	export default {
		props: {
			price: String,
			text: String,
			isActive: {
				type: Boolean,
				default: false
			}
		}
	}
</script>

<style>
	.tag {
		display: inline-block;
		cursor: pointer;
		border: none;
		background: linear-gradient(255.35deg, #DC3131 0.83%, rgba(255, 79, 79, 0) 108.93%), #FF5E56;
		border-radius: 50px;
		padding: 6px 12px;
		outline: none;

		font-weight: 400;
		font-size: 14px;
		line-height: 24px;
		color: #FFFFFF;
	}

	.tag:active {
		background: linear-gradient(255.35deg, #DC3131 0.83%, rgba(255, 79, 79, 0) 108.93%), #FF5E56;
	}

	.tag[isActive=false] {
		background: #EEF0F2;
		color: #808080;
	}
	.tag[isActive=false] .tag-price {
		color: #000000;
	}
	.tag[isActive=false]:hover {
		background: #DFE3E6;
	}
</style>