<<template>
  <div id="sample">
    <section id="title">
      <span>{{ title }}</span>
    </section>

    <section id="counter">
      <button @click="increment">Click!</button>
      <span>{{ count }}</span>
    </section>

    <section id="todo">
      <ul v-for="(item, index) in todos">
        <li>{{ item }}　<button @click="remove(index)">remove</button></li>
      </ul>
      <div>
        <input @keyup.enter="add"/>
      </div>
    </section>
  </div>
</template>

<script>
export default{
  data () {
    return {
      title: 'This is nuxt todo list'
    }
  },
  computed: {
    count: function () {
      return this.$store.state.counter.count
    },
    todos: function () {
      return this.$store.state.todo.list
    }
  },
  methods: {
    increment: function () {
      this.$store.commit('counter/increment')
    },
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