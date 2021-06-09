<template>
	<form class="input">
		<label class="input-label">{{label}}</label>
		<input 
			type="number" 
			class="input-view" 
			:placeholder="placeholder" 
			:necessarily="necessarily"
			v-model="inputValue"
			@input="getValue()"
		>
		<span 
			class="input-necessarily" 
			v-if="necessarily"
		>
			Поле обязательно для заполнения
		</span>
	</form>
</template>

<script>
	export default {
		props: {
			label: String,
			placeholder: String,
			necessarily: Boolean
		},
		data() {
			return {
				inputValue: ''
			}
		},
		methods: {
			getValue() {
				this.$emit('getValue', this.inputValue)	
			}
		}
	}
</script>

<style>
	input::-webkit-outer-spin-button,
	input::-webkit-inner-spin-button {
		display: none;
	}
	.input-label {
		font-weight: 500;
		font-size: 14px;
		line-height: 24px;
		color: #000000;
	}
	.input-view {
		border: 1px solid #BEC5CC;
		padding: 8px 10px;
		box-sizing: border-box;
		margin: 8px 0 4px;
		width: 100%;
		outline: none;
		border-radius: 3px;

		font-weight: normal;
		font-size: 14px;
		line-height: 24px;
		color: #000000;
	}
	.input-view:hover {
		border: 1px solid #000000;
	}
	.input-view::-webkit-input-placeholder { /* Edge */
		font-weight: normal;
		font-size: 14px;
		line-height: 24px;
		color: #BEC5CC;
	}

	.input-view:-ms-input-placeholder { /* Internet Explorer 10-11 */
		font-weight: normal;
		font-size: 14px;
		line-height: 24px;
		color: #BEC5CC;
	}

	.input-view::placeholder {
		font-weight: normal;
		font-size: 14px;
		line-height: 24px;
		color: #BEC5CC;
	}

	.input-necessarily {
		font-weight: normal;
		font-size: 10px;
		line-height: 12px;
		color: #EA0029;
	}
	.input-view[necessarily=true] {
		border: 1px solid #EA0029;
		border-radius: 3px;
	}
</style>