<template>
  <div>
    <ul class="list-group mt-5">
      <li
        class="list-group-item d-flex justify-content-between align-items-center" v-for="(task,index) in tasks" :key="index">
        <div class="col-4"> 
        {{task.name}}<br><small class="text-muted"><b-icon icon="clock"></b-icon> {{task.date}}</small>
        </div>
        <button class="btn btn-danger btn-sm" @click="deleteTask(index)"><b-icon icon="trash"></b-icon></button>
      </li>
    </ul>
  </div>
</template>
<script>
export default {
  name: "List",
  props: ["tasks"],
  methods: {
     deleteTask : function(index){
       this.$delete(this.tasks, index);
     },
  },

};
</script>
 

 