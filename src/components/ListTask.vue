<template>
  <div>
    Task Listesi
    <table>
      <thead>
        <tr>
          <td>Name</td>
          <td>Description</td>
          <td>Deadline</td>
        </tr>
      </thead>
      <tbody>
        <tr v-for="(task, index) in tasks" :key="index">
          <td>{{ task.name }}</td>
          <td>{{ task.description }}</td>
          <td>{{ task.deadline }}</td>
        </tr>
      </tbody>
    </table>
  </div>
</template>

<script>
import {eventBus} from "../event"
export default {
  name: "ListTask",
  data() {
    return {
      tasks: [
        {
          name: "name",
          description: "desc",
          deadline: "2022-03-31",
        },
        {
          name: "name",
          description: "desc",
          deadline: "2022-03-31",
        },
        {
          name: "name",
          description: "desc",
          deadline: "2022-03-31",
        },
      ],
    };
  },
  methods: {
      addNewTask(task){
          this.tasks.push(task);
      }
  },
  mounted() {
      eventBus.$on("newTaskCreated",this.addNewTask);
  },
  beforeDestroy(){
      eventBus.$off("newTaskCreated");
  }
};
</script>
