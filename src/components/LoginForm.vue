<template>
	<form @submit.prevent="submitForm">
		<div>
			<label for="username"></label>
			<input type="text" id="username" v-model="username" />
		</div>
		<div>
			<label for="password"></label>
			<input type="text" id="password" v-model="password" />
		</div>
		<button type="submit">로그인</button>
	</form>
</template>

<script>
import { loginUser } from '@/api/index';
export default {
	data() {
		return {
			username: '',
			password: '',
		};
	},
	methods: {
		async submitForm() {
			const userData = {
				username: this.username,
				password: this.password,
			};
			const response = await loginUser(userData);
			return response;
		},
	},
};
</script>

<style></style>
