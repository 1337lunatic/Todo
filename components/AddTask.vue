<template>
<div>
    <form @submit="onSubmit" class="add-form">
    <div class="form-control">
      	<label>Task</label>
      	<input 
		  type="text"
		  v-model="text" 
		  name="text" 
		  placeholder="Add Task" />
    </div>
    <div class="form-control">
      	<label>Day & Time</label>
      	<input
        type="text"
        v-model="day"
        name="day"
        placeholder="Add Day & Time"
      />
    </div>
    <div class="form-control form-control-check">
     	<label>Set Reminder</label>
     	<input 
		 type="checkbox" 
		 v-model="reminder" 
		 name="reminder" />
    </div>
    	<input type="submit" value="Save Task" class="btn btn-block" />
  	</form>
</div>

</template>

<script>
export default {
    name: 'AddTask',
    data: () => {
        return{
			text: '',
			day: '',
			reminder: false,
        }
    },

	methods:{
		onSubmit(e) {
			e.preventDefault()

			if (this.text === "") {
				alert("Please add text to the Task.")
				return
			}

			// Creating Task object
			const newTask = {
				name: this.text,
				day: this.day,
				reminder: this.reminder,
			}

			this.$emit('add-task',newTask)

			// Reset object
			this.text = ''
			this.day = ''
			this.reminder = false
		}
	},
}
</script>

<style scoped>


</style>