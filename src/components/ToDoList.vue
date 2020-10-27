<template>
  <div>
    <b-container>
      <b-row class="mt-4" v-for="(todo, index) in todos" :key="index" >
        <b-col cols="8" :class="[{line: todo.complete}, 'text-left']">
          <h5>{{todo.text}}</h5>
        </b-col>
        <b-col cols="4" class="text-right">
          <b-button @click="handleCompleteTodo(index)" :variant=" todo.complete ? '' : 'success' " >
            {{ todo.complete ? '完了' : '未完了' }}
          </b-button>
          <b-button @click="handleDeleteTodo(index)" variant="danger">削除</b-button>
        </b-col>
      </b-row>
    </b-container>
  </div>
</template>

<script>
export default {
  name: 'ToDoList',
  props: ['todos'],
  methods: {
    handleDeleteTodo(index) {
      this.$emit('DeleteTodo', index);
    },
    handleCompleteTodo(index) {
      this.$emit('CompleteTodo', index);
    },
  },
};
</script>

<style scoped>
  .line {
    text-decoration: line-through;
  }
</style>
