<template>
  <form @submit="handleSubmit" class="add-form">
    <div class="form-control">
      <label for="title">Tasks</label>
      <input v-model="title" type="text" name="title" placeholder="Add Task" />
    </div>
    <div class="form-control">
      <label for="day">Day &amp; Time</label>
      <input
        v-model="day"
        type="text"
        name="day"
        placeholder="Add Day &amp; Time"
      />
    </div>
    <div class="form-control form-control-check">
      <label for="reminder">Set Reminder</label>
      <input v-model="reminder" type="checkbox" name="reminder" />
    </div>
    <input type="submit" value="Save Task" class="btn btn-block" />
  </form>
</template>

<script>
export default {
  name: 'AddTask',
  data() {
    return {
      title: '',
      day: '',
      reminder: false,
    }
  },
  methods: {
    handleSubmit(e) {
      e.preventDefault()

      if (!this.title) {
        alert('Please add a task')
        return
      }

      const newTask = {
        // id: Math.floor(Math.random() * 100000),
        title: this.title,
        day: this.day,
        reminder: this.reminder,
      }
      // console.log(newTask)
      this.$emit('add-task', newTask)

      // clearing
      this.title = ''
      this.day = ''
      this.reminder = false
    },
  },
}
</script>

<style scope>
.add-form {
  margin-bottom: 40px;
}
.form-control {
  margin: 20px 0;
}
.form-control label {
  display: block;
}
.form-control input {
  width: 100%;
  height: 40px;
  margin: 5px;
  padding: 3px 7px;
  font-size: 17px;
}
.form-control-check {
  display: flex;
  align-items: center;
  justify-content: space-between;
}
.form-control-check label {
  flex: 1;
}
.form-control-check input {
  flex: 2;
  height: 20px;
}
</style>
