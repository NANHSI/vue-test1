<template>
  <img alt="Vue logo" src="./assets/rainbow.png" />
  <div class="ToDoList">
    <h1>{{ title }}</h1>
    <ul>
      <li v-for="(item, key) in items" :key="item.id">
        <span v-text="item.title"></span>
        <button @click="deleteItem(item.id)">Delete</button>
      </li>
    </ul>
    <input type="text" v-model="newItem" />
    <button @click="addnewItem">Add</button>
  </div>
</template>

<script>
export default {
  name: "ToDoList",
  todoText: "item.title",
  data() {
    return {
      title: "ToDoList",
      items: [
        {
          id: 1,
          title: "wake up",
        },
        {
          id: 2,
          title: "stay awake",
        },
        {
          id: 3,
          title: "find todolist",
        },
      ],
    };
  },
  methods: {
    deleteItem(id) {
      const toBeDeletedTodoListItemIndex = this.items.findIndex(
        (item) => item.id === id
      );
      this.items.splice(toBeDeletedTodoListItemIndex, 1);
    },
    addnewItem() {
      this.items.push({
        id: this.id,
        title: this.newItem,
      });
      this.id++;
      this.newItem = " ";
    },
  },
};
</script>

<style>
app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>

