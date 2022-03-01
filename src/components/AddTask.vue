<template>
  <div class="hello">
    <form>
      <input v-model="name" placeholder="Name" type="text" />
      <input v-model="description" placeholder="Desc" type="text" />
      <input v-model="deadline" type="date" />
      <button @click.prevent="saveTask">submit</button>
    </form>
    *******************************************************************
  </div>
</template>

<script>
import {eventBus} from "../event"

export default {
  name: "AddTask",

  data() {
    return {
      name: null,
      description: null,
      deadline: null,
    };
  },
  methods: {
    saveTask() {
      console.log("add task componenti içindeki saveTask methodu çalıştı eventBus emitlenecek");
      eventBus.$emit("newTaskCreated", this.createTaskObject());
    },
    createTaskObject(){
      return {
        name:this.name,
        description:this.description,
        deadline:this.deadline
      }
    }
  },
};
</script>

<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
