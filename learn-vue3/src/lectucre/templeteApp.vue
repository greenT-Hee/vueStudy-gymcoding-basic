<template>
	<h2>보간법</h2>
	<p>{{ message }}</p>
	<p v-once>{{ message }}</p>
	<button v-on:click="message += '🦖'">추가 버튼</button>
	<hr />
	<h2>v-html</h2>
	<p v-html="rawHTML"></p>
	<hr />
	<h2>속성 바인딩</h2>
	<div :title="dynamicTitle">마우스를 올려보세요</div>
	<input type="text" value="홍길동" :disabled="isDisabled" />
	<input v-bind="attrs" />
	<hr />
	<h2>JavaScript</h2>
	{{ message.split('').reverse().join('') }}
	{{ isDisabled ? 'NO' : 'YES' }}
</template>

<script>
import { ref } from 'vue';
export default {
	setup() {
		const message = ref('hello');
		const rawHTML = ref('<strong>안녕하세요</strong>');
		const dynamicTitle = ref('안녕하세요!!!!!!!!!!');
		const isDisabled = ref(true);
		const attrs = ref({
			type: 'password',
			value: '1234',
			disabled: false,
		});
		return {
			message,
			rawHTML,
			dynamicTitle,
			isDisabled,
			attrs,
		};
	},
};
</script>

<style lang="scss" scoped></style>
