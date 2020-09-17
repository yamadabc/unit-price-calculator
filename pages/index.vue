<template>
<div>
  <h1>坪単価計算</h1>
		<div class="container">
			<h2>売買</h2>
			<div class="row">
				<calculator></calculator>
			</div>
			<div class="row">
				<calculator></calculator>
			</div>
			<div class="row">
				<calculator></calculator>
			</div>
		</div>
		<div class='container'>
			<h2>賃貸</h2>
			<div class="row">
				<calculator></calculator>
			</div>
			<div class="row">
				<calculator></calculator>
			</div>
			<div class="row">
				<calculator></calculator>
			</div>
		</div>
</div>
</template>

<script>
import Vue from 'vue'
	import calculator from '~/components/Calculator.vue'

	export default Vue.extend({
		components: {
			calculator
		},
		data: function () {
			return {
				data: {
					price: '',
					area: '',
					unitPrice: '',
				},
			}
		},
	})
</script>
