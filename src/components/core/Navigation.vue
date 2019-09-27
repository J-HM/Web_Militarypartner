<template>
		<v-bottom-navigation 
			v-model="this.$route.name"
			color="primary" 
			shift 
			grow 
			:max-width=600
			class="mx-auto"
			:app="$vuetify.breakpoint.xsOnly"
			@change="change"
		>
			<v-btn value="question">
				<span>QnA</span>
				<v-icon>mdi-comment-question-outline</v-icon>
			</v-btn>

			<v-btn value="search">
				<span>Search</span>
				<v-icon>mdi-feature-search-outline</v-icon>
			</v-btn>

			<v-btn value="information">
				<span>Info</span>
				<v-icon>mdi-account-group-outline</v-icon>
			</v-btn>
		</v-bottom-navigation>
</template>

<script>
	export default {
		data: () => ({  }),
		methods: {
			change: function (index) {
				switch(index) {
					case "question":
						this.$router.push({ name: 'question' })
						break;
						
					case "search": 
						this.$router.push({ name: 'search' })
						break;
						
					case "information": 
						this.$router.push({ name: 'information' })
						break;
				}
			}
		},
	}
</script>