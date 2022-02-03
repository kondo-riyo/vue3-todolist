<template>
    <div>
        <!-- <ul>
        <li v-for="todo in state.todoList" :key="todo.todo">{{ todo.todo }}</li>
        </ul> -->
        <Todo-input />
    </div>
</template>

<script lang="ts">
//defineComponent = 型推論が効くようになる----------
import { defineComponent } from 'vue';
import TodoInput from '../components/TodoInput.vue';

export default defineComponent({
  name: 'TodoList',
  components: {
    TodoInput
  },
//   setup() {
//     // lang="ts"とした場合。 reactiveの中で型定義を行います。
//     // 仮データを二つ用意したため、二つtodo定義しています。本来は不必要です。
//     const state = reactive<{ todoList: [{todo: String}, {todo: String}];}>({
//       todoList: [
//           {todo: 'todo1'},
//           {todo: 'todo2'}

//       ]
//     });
//     return { state };
//   }
});
</script>
