<template>
	<div class="popap">
		<div class="popap-view">
			<div>
				<button 
					class="popap-close"
					@click="closePopup()"
				>
					<img src="../assets/icons/close.svg" alt="close">
				</button>
				<slot></slot>
			</div>
			<BigButton text="Добавить"/>
		</div>
	</div>
</template>
<script>
	import BigButton from '@/components/bigButton'
	export default {
		components: {
			BigButton
		},
		methods: {
			closePopup() {
				this.$emit('closePopup');
			}
		}
	}
</script>

<style>
	.popap {
		position: fixed;
		top: 0;
		right: 0;
		bottom: 0;
		left: 0;

		overflow: auto;
		padding: 120px 0 92px;
		
		background: rgba(0, 0, 0, 0.3);
	}
	.popap-view {
		max-width: 453px;
		width: 100%;
		margin: 0 auto;
		position: relative;
		padding: 32px;
		box-sizing: border-box; 
		border-radius: 30px;
		background: #FFFFFF;

		display: flex;
		justify-content: space-between;
		flex-flow: column;

	}
	.popap-close {
		position: absolute;
		top: 27px;
		right: 23px;
		width: 18px;

		background: none;
		border: none;
		padding: 0;
		cursor: pointer;
	}
	@media only screen and (max-width: 320px) {
        .popap {
			padding: 0;
		}
		.popap-view {
			width: 100%;
			height: 100%;
			margin: 0;
			padding: 16px;
			padding-top: 32px;
			border-radius: 0;
		}
		.popap-close {
			position: absolute;
			top: 16px;
			right: 16px;
			width: 12px;
		}
    }
</style>