<script setup>
import { ref } from 'vue';
import Search from '@components/Inputs/Search.vue';
import UserInfo from '@components/User/UserInfo.vue';
import Button from '@components/Button/Button.vue';
import Badge from '@components/Badge/Badge.vue';
import Offcanvas from '@components/Offcanvas/Offcanvas.vue';
import Popup from '../components/Popup/Popup.vue'

const props = defineProps(['title']);
const data = ref({
	image: 'https://avatars.githubusercontent.com/u/2681643',
	name: 'Tolga Eğilmezel',
	email: 'egilmezel@tolga.com'
})

const toggleNotification = ref(false);
const toggle = ref(false);

const toggleHandler = () => {
	toggleNotification.value = !toggleNotification.value;
};
const searchHandler = (value) => {
	alert(value);
}
const togglePopup = () => {
	toggle.value = !toggle.value;
}

</script>
	
<template>
	<header class="header">
		<div class="header__title">
			{{ title }}
		</div>
		<div class="header__content">
			<Search placeholder="Search" @search="searchHandler" />
		</div>
		<div class="header__actions">
			<div class="btn-group">
				<Button icon="chat" variant="icon" classes="text-strong" />
				<Badge icon="notifications" active @click="toggleHandler" />
				<Button icon="settings" variant="icon" classes="text-strong" />
			</div>
			<UserInfo class="userinfo" :data="data" @click="togglePopup" />
			<Popup v-if="toggle" @show="togglePopup"></Popup>
		</div>
		<Offcanvas v-model:show="toggleNotification">
			<template #header>
				<h3 class="text-secondary">Notification</h3>
			</template>
			<template #body>
			</template>
		</Offcanvas>
	</header>
</template>

<style scoped>
.userinfo:hover {
	cursor: pointer;
}
</style>