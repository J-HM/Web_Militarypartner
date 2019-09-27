<template>
	<v-row justify="center">
		<v-col cols=11 sm=11 md=10 lg=8 xl=6>
			<v-data-table
				v-model="selected"
				:headers="headers"
				:items="desserts"
				item-key="name"
				:page.sync="page"
				show-select
				:items-per-page="10" 
				class="elevation-5 mx-auto"
				@page-count="pageCount = $event"
				hide-default-footer
			>
			<template v-slot:header.data-table-select="{ on, props }">
				<v-simple-checkbox class = "d-none"/>
			</template>
			<template v-slot:item.data-table-select="{ isSelected, select }">
				<v-simple-checkbox color="teal" :value="isSelected" @input="select($event)"/>
			</template>
		</v-data-table>
		</v-col>
				
		<v-col cols=12>
			<v-pagination v-model="page" :length="pageCount"></v-pagination>
		</v-col>
		<select>
			
		</select>
	</v-row>
</template>

<script>
	export default {
		components: {
			select: () => import ('@/components/contents/Select')
		},
		
		data() {
			return {
				page: 1,
				pageCount: 0,
				itemsPerPage: 10,
				selected: [],
				headers: [{
						text: '특기',
						align: 'left',
						sortable: false,
						value: 'name',
					},
					{
						text: '입영일',
						value: 'calories'
					},
					{
						text: '전역일',
						value: 'fat'
					},
					{
						text: 'Carbs (g)',
						value: 'carbs'
					},
					{
						text: 'Protein (g)',
						value: 'protein'
					},
					{
						text: 'Iron (%)',
						value: 'iron'
					},
				],
				desserts: [{
						name: 'Frozen Yogurt',
						calories: 159,
						fat: 6.0,
						carbs: 24,
						protein: 4.0,
						iron: '1%',
					},
					{
						name: 'Ice cream sandwich',
						calories: 237,
						fat: 9.0,
						carbs: 37,
						protein: 4.3,
						iron: '1%',
					},
					{
						name: 'Eclair',
						calories: 262,
						fat: 16.0,
						carbs: 23,
						protein: 6.0,
						iron: '7%',
					},
					{
						name: 'Cupcake',
						calories: 305,
						fat: 3.7,
						carbs: 67,
						protein: 4.3,
						iron: '8%',
					},
					{
						name: 'Gingerbread',
						calories: 356,
						fat: 16.0,
						carbs: 49,
						protein: 3.9,
						iron: '16%',
					},
					{
						name: 'Jelly bean',
						calories: 375,
						fat: 0.0,
						carbs: 94,
						protein: 0.0,
						iron: '0%',
					},
					{
						name: 'Lollipop',
						calories: 392,
						fat: 0.2,
						carbs: 98,
						protein: 0,
						iron: '2%',
					},
					{
						name: 'Honeycomb',
						calories: 408,
						fat: 3.2,
						carbs: 87,
						protein: 6.5,
						iron: '45%',
					},
					{
						name: 'Donut',
						calories: 452,
						fat: 25.0,
						carbs: 51,
						protein: 4.9,
						iron: '22%',
					},
					{
						name: 'KitKat',
						calories: 518,
						fat: 26.0,
						carbs: 65,
						protein: 7,
						iron: '6%',
					},
				],
			}
		},
	}
</script>