<template>
  <div>
    <div class="container">
      <div class="row justify-content-center" style="margin-top:100px">
        <div class="col-md-8">
          <form class="input-group" v-on:submit.prevent="AddTodo">
            <input type="text" class="form-control" placeholder="Enter new task" v-model="name" />
            <b-form-datepicker v-model="date"></b-form-datepicker>
            <div class="input-group-append">
              <button class="btn btn-info" :disabled="!name || !date">+ Add</button>
            </div>
          </form>
           <List v-bind:tasks="tasks"/>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import List from '../../components/todos/List'
export default {
  name: "Create",
  components :{
     List
  },
  data() {
    return {
      tasks: [],
      name: "mouloud",
      date: ""
    };
  },
  methods: {
    AddTodo() {
      this.tasks.unshift({
        name: this.name,
        date: this.date,
        status: false,
      });
    }
  }
};
</script>

<style>
</style>