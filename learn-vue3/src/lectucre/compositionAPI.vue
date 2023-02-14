<template>
	<div>
		<h2>반응형</h2>
		<p>{{ reactiveMessage }}</p>
		<button v-on:click="addReactiveMsg">Add message</button>
		<h2>일반</h2>
		<p>{{ normalMesssage }}</p>
		<button v-on:click="addNoramlMsg">Add message</button>
	</div>
</template>

<script>
import { ref } from 'vue';

export default {
	setup() {
		// 반응형 상태 선언
		const reactiveMessage = ref('reactive message 🐰');
		const addReactiveMsg = () => {
			reactiveMessage.value += '🥕';
		};

		// 일반 변수 선언
		const normalMesssage = 'normal message 🫥';
		const addNoramlMsg = () => {
			// normalMesssage = normalMesssage + '!';  반응형이 아님 (error)
		};

		return {
			reactiveMessage,
			normalMesssage,
			addReactiveMsg,
			addNoramlMsg,
		};
	},
};
</script>

<style lang="scss" scoped></style>
