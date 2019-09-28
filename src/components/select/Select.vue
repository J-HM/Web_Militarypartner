<template>
	<div class="text-center">
		<v-dialog v-model="dialog" width="1000">
			<template v-slot:activator="{ on }">
				<v-btn 
					v-if=true 
					v-on="on"
					bottom right fixed 
					color="pink" 
					dark 
					fab >
					<v-icon>mdi-plus</v-icon>
				</v-btn>
			</template>

			<v-card>
				<v-card-text>
					<calendar />
				</v-card-text>

				<v-card-actions>
					<div class="flex-grow-1"></div>
					<v-btn color="primary" text @click="dialog = false">
						I accept
					</v-btn>
				</v-card-actions>
			</v-card>
		</v-dialog>
	</div>
</template>

<script>
	export default {
		components: {
			Calendar: () => import ('@/components/select/Calendar'),
		},
		
		data: () => ({
			dialog: false,
		}),
	}
</script>