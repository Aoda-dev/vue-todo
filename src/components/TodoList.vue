<template>
  <div class="list">
    <ul>
      <TodoItem v-for="(t, i) in todos" v-bind:todo="t" v-bind:key="t.id" v-bind:index="i" v-on:remove="removeTodo" />
    </ul>
  </div>
</template>

<script>
import TodoItem from '@/components/TodoItem'

export default {
  name: 'TodoList',
  props: ['todos'],
  components: {
    TodoItem,
  },
  methods: {
    removeTodo(id) {
      this.$emit('remove-todo', id)
    },
  },
}
</script>

<style scoped>
.list {
  width: 700px;
  margin: 50px auto;
}

ul {
  list-style: none;
  margin: 0;
  padding: 0;
}
</style>
