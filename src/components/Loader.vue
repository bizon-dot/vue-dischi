<template>
	<div class="loader">
		<img src="https://upload.wikimedia.org/wikipedia/commons/thumb/1/17/Yin_yang.svg/512px-Yin_yang.svg.png" />
	</div>

</template>

<script>
	export default {
		name: 'Loader',

	}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
	@import './style/general';

	.loader {
		position: fixed;
		top: 0;
		left: 0;
		display: flex;
		flex-direction: column;
		justify-content: center;
		align-items: center;
		width: 100%;
		height: 100%;
		background-color: white;
	}

	img {
		width: em(300);
		margin: 1rem 0;
		animation: rotate 1s infinite
	}

	@keyframes rotate {
		from {
			transform: rotate(0deg);
		}

		to {
			transform: rotate(359deg);
		}
	}
</style>