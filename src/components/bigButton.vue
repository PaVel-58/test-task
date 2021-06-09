<template>
	<button class="bigButton" :light="light" :disabled="disabled">
		{{text}}
	</button>
</template>

<script>
	export default {
		props: {
			text: String,
			light: Boolean,
			disabled: Boolean
		}
	}
</script>

<style>
	.bigButton {
		cursor: pointer;
		background: linear-gradient(255.35deg, #DC3131 0.83%, rgba(255, 79, 79, 0) 108.93%), #FF5E56;
		border: none;
		box-shadow: 0px 0px 24px rgba(234, 0, 41, 0.33);
		border-radius: 6px;
		padding: 16px 0;
		width: 100%;

		font-weight: 500;
		font-size: 16px;
		line-height: 24px;
		color: #FFFFFF;
	}
	.bigButton:hover {
		background: #EA0029;
	}

	.bigButton[light=true] {
		border: 1px solid #FFFFFF;
		background: transparent;
		width: auto;
		padding: 16px 32px;
	}
	.bigButton[light=true]:hover {
		border: 1px solid #FFFFFF;
		background: #fff;
		color: #000;
	}

	.bigButton:disabled {
		background: #BEC5CC;
		color: #FFFFFF;
		box-shadow: none;
	}
	.bigButton:disabled:hover {
		background: #BEC5CC;
		color: #FFFFFF;
		box-shadow: none;
	}
	@media only screen and (max-width: 320px) {
        .bigButton {
			font-size: 12px;
			line-height: 16px;
			padding: 12px 0;	
		}
		.bigButton[light=true] {
			padding: 12px 24px;
		}
    }
</style>