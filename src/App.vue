<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png" />
    <AddTask />
    <ListTask />
  </div>
</template>

<script>
import AddTask from "./components/AddTask.vue";
import ListTask from "./components/ListTask.vue";

export default {
  name: "App",
  components: {
    AddTask,
    ListTask,
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>

<!--
tasks : [
        {
          name:"name",
          description:"desc",
          deadline:"2022-03-31"
        },
        {
          name:"name",
          description:"desc",
          deadline:"2022-03-31"
        },
        {
          name:"name",
          description:"desc",
          deadline:"2022-03-31"
        }
      ]
-->
