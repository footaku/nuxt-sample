<template>
  <section>
    <div>
      <input @keyup.enter="add"/>
    </div>
    <ul v-for="(item, index) in todos" v-bind:key="index">
      <li>{{ item }}　<button @click="remove(index)">remove</button></li>
    </ul>
  </section>
</template>

<script>
export default{
  computed: {
    todos: function () {
      return this.$store.state.todo.list
    }
  },
  methods: {
    add: function (e) {
      this.$store.commit('todo/add', e.target.value)
      e.target.value = ''
    },
    remove: function (index) {
      this.$store.commit('todo/remove', index)
    }
  }
}
</script>
