<<template>
  <div id="sample">
    <section id="title">
      <span>{{ title }}</span>
    </section>
    <todoItem />
  </div>
</template>

<script>
import todoItem from '~/components/todo-item.vue'

export default{
  data () {
    return {
      title: 'This is todo list sample'
    }
  },
  components: {
    todoItem
  }
}
</script>