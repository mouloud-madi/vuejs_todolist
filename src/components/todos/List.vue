<template>
  <div>
    <ul>
      <li v-for="(task,index) in tasks" :key="index">{{task.name}}</li>
    </ul>
  </div>
</template>

<script>
export default {
  name: "List",
  props: ["tasks"]
};
</script>
 

 