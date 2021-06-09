<template>
	<button class="textButton">
		{{text}}
	</button>
</template>

<script>
	export default {
		props: {
			text: String
		}
	}
</script>

<style>
	.textButton {
		background: none;
		border: none;
		padding: 0;
		cursor: pointer;
		font-size: 14px;
		line-height: 24px;
		font-weight: 500;
		color: #EA0029;
	}
	.textButton:hover {
		color: #F53A31;
	}
</style>