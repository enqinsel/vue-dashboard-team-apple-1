<script setup>
import Progress from '@components/Progress/Progress.vue';
import Button from '@components/Button/Button.vue';
import Widget from '@components/Widget/Widget.vue';
import Avatar from '@components/Avatar/Avatar.vue';
import Tag from '@components/Tag/Tag.vue';

const props = defineProps(['data']);
</script>
	
<template>
	<div class="card">
		<div class="card__header">
			<p>{{props.data.Project_Name}}</p>
			<div class="btn-group btn-group--sm">
				<Button icon="edit" variant="icon" classes="card__header__button" />
				<Button icon="more_vert" variant="icon" classes="card__header__button" />
			</div>
		</div>
		<div class="card__content">
			<div class="gird">
				<div class="grid__col">
					<template v-if="props.data.Status === 1">
						<Tag name="Active" variant="success" icon="fiber_manual_record" />
					</template>
					<template v-if="props.data.Status === 0">
						<Tag name="Inactive" variant="danger" icon="fiber_manual_record" />
					</template>
					<template v-if="props.data.Status === 2">
						<Tag name="On hold" variant="warning" icon="fiber_manual_record" />
					</template>
				</div>
				<div class="grid__col">
					<p class="fs-sm text-fade mb-1">Start Date</p>
					{{props.data.Start_Date}}
				</div>
				<div class="grid__col">
					<div class="widget-group">
						<Widget :data="{ piece: props.data.Task_Count, name: 'Tasks' }" />
						<Widget :data="{ piece: props.data.Member, name: 'Members' }" />
					</div>
				</div>
				<div class="grid__col">
					<p class="fs-sm text-fade mb-1 text-strog">Members</p>
					<div class="avatar-group">
						<Avatar v-for="employee in props.data.Employees " :key="employee" :image="employee.Employee_Avatar"
							size="32" />
						<Button icon="add" variant="circle" />
					</div>
				</div>
			</div>
		</div>
		<div class="card__action">
			<Progress name="Progress" :value="props.data.Complated" :max="100" />
		</div>
	</div>
</template>
	
<style lang="scss">
.card {
	width: 100%;
	background: #FFFFFF;
	border: 1px solid #E5E5E5;
	border-radius: 8px;
	transition: all 0.3s ease-in-out;
	padding: 24px;
	display: flex;
	flex-direction: column;
	gap: 22px;

	&:hover {
		box-shadow: rgba(35, 35, 104, 0.2) 0px 7px 29px 0px;
		border-color: #fff;
	}

	&__header {
		display: flex;
		justify-content: space-between;
		align-items: center;
		gap: 16px;

		p {
			font-size: 18px;
			font-weight: 500;
			color: var(--color-secondary);
		}
	}

	// &__content {}

	// &__action {}
}

.gird {
	display: grid;
	gap: 16px;
	grid-template-areas:
		"a a a"
		"b b c"
		"d d d";

	.grid__col {
		&:first-child {
			grid-area: a;
		}

		&:nth-child(2) {
			grid-area: b;
		}

		&:nth-child(3) {
			grid-area: c;
			display: flex;
			justify-content: end;
			align-items: center;
		}

		&:last-child {
			grid-area: d;
		}
	}
}
</style>