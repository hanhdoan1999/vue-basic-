<template lang="">
    <div >
    <ul>
        <li
        v-for="todo in todos"
        :key="todo.id"
        >{{todo.title}}</li>
  </ul>
    </div>
</template>
<script>
export default {
    data() {
        return {
            todos: [
      {
        id: 1,
        title: 'Do the dishes',
      },
      {
        id: 2,
        title: 'Take out the trash',
      },
      {
        id: 3,
        title: 'Mow the lawn'
      }
    ],
        }
    },
}
</script>
<style lang="">
    
</style>