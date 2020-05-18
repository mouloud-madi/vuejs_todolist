<template>
  <div>
    <div class="container">
      <div class="row justify-content-center" style="margin-top:100px">
        <div class="col-md-8">
          <form class="input-group" v-on:submit.prevent="AddTodo">
            <input type="text" class="form-control" placeholder="Enter new task" v-model.trim="name" />
            <b-form-datepicker v-model="date"></b-form-datepicker>
            <b-form-timepicker v-model="time" ></b-form-timepicker>
            <div class="input-group-append">
              <button class="btn btn-info" :disabled="!name"><b-icon icon="plus"></b-icon> Add</button>
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
import moment from 'moment'
export default {
  name: "Create",
  components :{
     List
  },
  data() {
    return {
      tasks: [],
      name: "",
      date: "",
      time: ""
    };
  },
  methods: {
    AddTodo() {
      this.tasks.unshift({
        name: this.name,
        date: this.date ? moment(this.date).format("D/M/YYYY") : moment().format("D/M/YYYY"),
        time: this.time ? this.time : moment().format("HH:mm:ss"),
        status: false,
      }); 
      this.name=""
      this.date=""
      this.time=""
    }
  }
};
</script>

<style>
</style>