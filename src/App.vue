<template>
  <div id="app">
    <h2>TodO aPp</h2>
    <Todo />
  </div>
</template>

<script>
import Todo from "./components/Todo.vue";
export default {
  name: "App",
  components: {
    Todo,
  },
};
</script>

<style>
#app {
  background-color: #e2e5f1;
  height: 100vh;
  padding-top: 2rem;
}
h2 {
  font-family: "Lobster", cursive;
  color: #163591;
  text-align: center;
  text-shadow: 1px 1px 2px gray, 1px 1px 2px black, 5px 5px 5px grey;
  margin-top: 25px;
  font-size: 40px;
  padding: 10px;
  margin-bottom: 1rem;
  letter-spacing: 3px;
}
::-webkit-scrollbar {
  width: 5px;
}

/* Track */
::-webkit-scrollbar-track {
  box-shadow: inset 0 0 5px grey; 
  border-radius: 10px;
}
 
/* Handle */
::-webkit-scrollbar-thumb {
  background: #163591; 
  border-radius: 10px;
}

/* Handle on hover */
::-webkit-scrollbar-thumb:hover {
  background: #163591; 
}
</style>
