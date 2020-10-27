<template>
  <b-container>
    <b-input-group>
      <b-form-input type="text" v-model="value" />
      <b-input-group-append>
        <b-button variant="info" @click="AddTodo">送信</b-button>
      </b-input-group-append>
    </b-input-group>
  </b-container>
</template>

<script>
export default {
  data() {
    return {
      value: '',
    };
  },
  methods: {
    AddTodo() {
      this.$emit('AddTodo', this.value);
      this.value = '';
    },
  },
};
</script>
