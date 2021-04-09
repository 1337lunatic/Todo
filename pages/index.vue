<template>
    <div class="container">
        <div class="todoApp">
            <div class='title'>
                Todo items
            </div>
			<div>
				<todo-container :todoitems='todoItems'></todo-container>
			</div>
        </div>
    </div>
</template>

<script>
import todoContainer from '~/components/todo-container.vue'
export default {
  components: { todoContainer },
	data: () =>{
		return {
			todoItems: [
				{
					ID: 1,
					name: "Wash clothes",
					checked: false
				},
				{
					ID: 2,
					name: "Buy milk",
					checked: false
				},	
				{
					ID: 3,
					name: "Git gut",
					checked: false
				},
				{
					ID: 4,
					name: "Sleep",
					checked: false
				}
			]
		}
	}
}
</script>

<style lang='scss'>
@import '~/assets/css/config';
.container {
  	margin: 0 auto;
  	min-height: 100vh;
  	display: flex;
  	justify-content: center;
  	text-align: center;
 
	.title {
  		font-family:
  		  'Quicksand',
  		  'Source Sans Pro',
  		  -apple-system,
  		  BlinkMacSystemFont,
  		  'Segoe UI',
  		  Roboto,
  		  'Helvetica Neue',
  		  Arial,
  		  sans-serif;
  		display: block;
  		font-weight: 300;
  		font-size: 100px;
  		color: #35495e;
  		letter-spacing: 1px;
	}
	.subtitle {
		font-weight: 300;
		font-size: 42px;
		color: #526488;
		word-spacing: 5px;
		padding-bottom: 15px;
	}

	.links {
		padding-top: 15px;
	}
}



</style>
