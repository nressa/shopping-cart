<template>
	<div>
		<h1>Shoppping Cart</h1>

		<ul>
			<li v-for="product in products">
				{{ product.title }}
				- {{ product.price | currency }}
				- {{ product.quantity }}
			</li>
		</ul>
		<br/>
		<p>Total: {{ total| currency }}</p>
		<button @click="$store.dispatch('checkout')">Checkout</button>
		<p v-if="$store.state.checkoutStatus"> {{ $store.state.checkoutStatus }} </p>
	</div>
</template>

<script>
	export default {
		computed: {
			products(){
				return this.$store.getters.cartProducts
			},

			total(){
				return this.$store.getters.cartTotal
			}
		},
	}
</script>

<style scoped>
	
</style>
