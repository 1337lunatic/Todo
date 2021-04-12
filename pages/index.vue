<template>
    <div class="container">
        <div class="todoApp">
            <div class='title'>
                Todo items
            </div>
			<div style="justify-content:center; display: flex;">
				<AddTask @add-task="$emit('add-task')"/>
			</div>
			<div>
				<Tasks @delete-task="DeleteTask" :tasks="tasks"></Tasks>
			</div>
        </div>
    </div>
</template>

<script>
import { created } from 'vue'
import Tasks from '~/components/Tasks.vue'
import AddTask from '~/components/AddTask.vue'

export default {
  components: { 
	  Tasks,
	  AddTask,
	},

	data: () =>{
		return {
			tasks: []
		}
	},

	methods:{
		DeleteTask(id){
			this.tasks = this.tasks.filter((task) => task.id !== id)
		},
	},

	created() {
		this.tasks = [
				{
					id: 1,
					name: "Wash clothes",
					checked: false,
					reminder: true,
					day: 'April 10th @ 10:00',
				},
				{
					id: 2,
					name: "Buy milk",
					checked: false,
					reminder: true,
					day: 'April 10th @ 11:00',
				},	
				{
					id: 3,
					name: "Git gut",
					checked: false,
					day: 'April 7th @ 15:00',
					reminder: true,
				},
				{
					id: 4,
					name: "Sleep",
					checked: false,
					day: 'April 7th @ 22:00',
					reminder: false,
				}
		]
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
