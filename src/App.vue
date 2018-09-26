<script>
import CcUsers from './components/users/main.vue'
import { mapState, mapActions } from 'vuex'

export default {
	name: 'CodecastsApp',
	mounted() {
		const payload = {
			name: 'Fabio Vedovelli',
			email: 'vedovelli@gmail.com',
			level: 'admin-da-desgraça-toda',
			city: 'Santo André',
			state: 'SP',
		}
		setTimeout(() => {
			this.changeUser(payload)
			// this.$store.commit('CHANGE_USER', payload) //old version
		}, 3000)
	},
	components: {
		CcUsers
	},
	methods: {
		...mapActions(['changeUser'])
	},
	computed: {
		...mapState({
			user: state => {
				const { name, email } = state.user
				return `O usuario logado é ${name} 
		 			e possui o email ${email}.`
			}
		})
	}
}
</script>

<template>
	<div>
		<h1>Welcome Vue2</h1>
		<h4>{{ user }}</h4>
		<hr>
		<cc-users></cc-users>
	</div>
</template>
