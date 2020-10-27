<template>
  <div>
    <h1>TODOリスト</h1>
    <to-do-form  @AddTodo="AddTodo" />
    <to-do-list :todos="todos" @DeleteTodo="DeleteTodo" @CompleteTodo="CompleteTodo"/>
  </div>
</template>

<script>
import ToDoForm from '@/components/ToDoForm';
import ToDoList from '@/components/ToDoList';

export default {
  name: 'Todo',
  components: {
    ToDoForm,
    ToDoList,
  },
  data() {
    return {
      todos: [],
    };
  },
  methods: {
    AddTodo(value) {
      if (value) {
        this.todos.unshift({ text: value, complete: false });
      }
    },
    DeleteTodo(index) {
      this.todos.splice(index, 1);
    },
    CompleteTodo(index) {
      this.todos[index].complete = !this.todos[index].complete;
    },
  },
};
</script>

