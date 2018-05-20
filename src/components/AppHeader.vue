<template>
	<div class="ui secondary pointing menu">
		<router-link to="/" class="active item" href="#">
			Image Storage
		</router-link>
		<div class="right menu">
			<div v-if="isLoggedIn" class="horizontal">
				<router-link to="/" class="ui item" href="#">
					Galleries
				</router-link>
				<router-link to="/upload" class="ui item" href="#">
					Upload
				</router-link>
				<a class="ui item" href="#" @click="logout">
					Log out
				</a>
			</div>
			<div v-else class="right menu">
				<a class="ui item" href="#" @click="login">
					Log in
				</a>
			</div>
		</div>
	</div>
</template>

<script>
	import { mapActions, mapGetters } from 'vuex';

	export default {
		name: 'AppHeader',
		methods: mapActions(['login', 'logout']),
		computed: mapGetters(['isLoggedIn'])
	}
</script>

<style scoped>
	.horizontal {
		display: flex;
		flex-direction: row;
	}
</style>