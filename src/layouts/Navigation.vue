<script setup>
	import { ref } from 'vue'
	import Button from '@components/Button/Button.vue';
	import Tabs from '@components/Tabs/Tabs.vue';
	import Dropdown from '@components/Dropdown/Dropdown.vue';
	
	const tabPanes = ref(['All', 'Inactive', 'On hold', 'Complated']);
	const dropİtems = ref(['Default', 'Important', 'Priority']);
	const dropValue = ref('Default');
	const activeTab = ref('');
	
	</script>
	
	<template>
			<div class="nav">
					<Button name="New" icon="add" variant="primary" classes="rounded" />
					<div class="nav__content">
							<Tabs :panes="tabPanes" v-model:active="activeTab" />
							<Dropdown :items="dropİtems" v-model:value="dropValue" icon="filter_list" />
					</div>
			</div>
	</template>
	
	<style lang="scss">
	.nav {
			display: flex;
			align-items: center;
			justify-content: space-between;
			gap: 30px;
			padding: 0 30px 30px 30px;
			position: sticky;
			&__content {
					flex: 1;
					border: 1px solid #F1F2F7;
					border-radius: 8px;
					display: flex;
					align-items: center;
					justify-content: space-between;
					padding: 10px 30px;
			}
	}
	</style>