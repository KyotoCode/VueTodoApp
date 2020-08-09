<template>
  <div id="app">
    <main>
      <h1>ToDoApp</h1>
      <input
        class="u-full-width"
        type="text"
        v-model="todoText"
        placeholder="Enter todo"
        id="inputDos"
      />
      <button class="button-primary" @click="btnSub" id="submitBtn">Button element</button>
    </main>
    <hr />
    <section>
      <ul>
        <li v-for="(todo, i) in existingTodo" :key="(todo.name, i)">
          <span>{{i + 1}}: {{todo.name}}</span>
          <button @click="btnDelete(i)">Remove</button>
        </li>
      </ul>
    </section>
  </div>
</template>

<script>
export default {
  name: "App",
  data() {
    return {
      todoText: "",
      existingTodo: [
        { name: "go shoping", id: 1 },
        { name: "go to school", id: 2 },
      ],
    };
  },
  methods: {
    btnSub() {
      this.existingTodo.push({
        name: this.todoText,
      });
    },
    btnDelete(i) {
      this.existingTodo.splice(i, 1);
    },
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
#inputDos {
  text-align: center;
  width: 50%;
}
#todos {
  display: flex;
  justify-content: center;
}
#todos button {
  margin-left: 50px;
}
hr {
  width: 80%;
}
ul button {
  margin-left: 50px;
}
</style>
