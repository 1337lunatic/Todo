<template>
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

<style lang="scss" scoped>
@import '~/assets/css/config';
// @include primary-text;

.add-form{
	@include primary-text;
	border: 1px solid black;
	padding: 0 5px;	
	margin: 20px 0;
	width: 340px;
	align-self: center;

	.form-control{
		display: flex;
		flex-direction: column;
		width: 100%;
		height: 40%;
		margin: 7px 0;
		align-content: flex-start;



		& > label{
			display: block;
			align-self: flex-start;
		}
		& > input{
			flex: 1;
		}
	}
}
</style>