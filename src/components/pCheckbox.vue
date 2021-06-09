<template>
	<button 
		class="checkbox"
		:class="{active: isActive}"
		:disabled="disabled"
	>
		<img src="../assets/icons/checkMark.svg" alt="check">
	</button>
</template>

<script>
	export default {
		props: {
			isActive: {
				type: Boolean,
				default: false
			},
			disabled: {
				type: Boolean,
				default: false
			}
		}
	}
</script>

<style>
	.checkbox {
		border: 1px solid #DFE3E6;
		border-radius: 6px;
		width: 20px;
		height: 20px;
		background: none;
		cursor: pointer;
		padding: 4px 3px 5px 2px;
		box-sizing: border-box;

		text-align: center;
		font-size: 0;
	}
	.checkbox:hover {
		border: 1px solid #000;
	}
	.checkbox.active {
		border: 1px solid #FF5E56;
		background: linear-gradient(255.35deg, #DC3131 0.83%, rgba(255, 79, 79, 0) 108.93%), #FF5E56;
		border-radius: 6px;
	}
	button.checkbox:disabled {
		border: 1px solid #BEC5CC;
		background: #BEC5CC;
		border-radius: 6px;
	}
</style>