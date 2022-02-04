<template>
  <div id="app">
    <h1>Todoリスト</h1>
    <input v-model="data.todo"><br>
    <button @click="addTodo">追加</button>
    <ul>
      <li v-for="(todo, index) in data.todos" :key="index">
        {{ todo }} 
        <button @click="removeTodo(index)">×</button>
      </li>
    </ul>
  </div>
</template>

<script>
  // import { reactive } from 'vue';
  import { ref } from 'vue';
  
export default {
  // data() {
  //   return {
  //     todo: '',
  //     todos:[]
  //   }
  // },
  // methods: {
  //   addTodo() {
  //     this.todos.push(this.todo)
  //     this.todo = ''
  //   },
  //   removeTodo(index) {
  //     this.todos.splice(index, 1)
  //   }
  // }
  setup() {
    //reactiveの場合----------------------------
    // let data = reactive({
    //   todo: '',
    //   todos:[]
    // });
    // const addTodo = () => {
    //   data.todos.push(data.todo)
    //   data.todo = ''
    // };
    // const removeTodo = index => {
    //   data.todos.splice(index, 1)
    // };
    // return { data , addTodo, removeTodo };

    //refの場合---------------------------------
    let data = ref({
      todo: '',
      todos:[]
    });
    const addTodo = () => {
      data.value.todos.push(data.value.todo)
      data.value.todo = ''
    };
    const removeTodo = index => {
      data.value.todos.splice(index, 1)
    };
    return { data, addTodo, removeTodo };
  }
}
</script>

<style>
</style>