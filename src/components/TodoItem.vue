<template>
  <li>
    <span v-bind:class="{ active: todo.completed }">
      <input type="checkbox" v-model="check" v-on:change="todo.completed = !todo.completed" />
      <strong>{{ index + 1 }}</strong>
      {{ todo.title }}
    </span>
    <button v-on:click="$emit('remove', todo.id)">&times;</button>
  </li>
</template>

<script>
export default {
  name: 'TodoItem',
  props: {
    todo: {
      type: Object,
      required: true,
    },
    index: {
      type: Number,
      required: true,
    },
  },
  data() {
    return {
      check: this.todo.completed,
    }
  },
}
</script>

<style scoped>
li {
  border: 1px solid #ccc;
  display: flex;
  justify-content: space-between;
  padding: 0.5rem 2rem;
  margin-bottom: 1rem;
}

button {
  outline: none;
  border: 0;
  background: red;
  color: #fff;
  border-radius: 50%;
  font-weight: bold;
}

.active {
  text-decoration: line-through;
}
</style>
