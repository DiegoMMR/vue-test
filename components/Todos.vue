<template>
  <div>
    <h2 @click="test">Todos</h2>
    <div class="scroll-div">      
      <ul class="list-group list-group-flush">
        <li class="list-group-item" v-for="item in todos" :key="item.userId">
          {{item.title}}
          <span :class="'badge badge-pill badge-' + (item.completed ? 'success' : 'danger')">{{item.completed ? 'compete' : 'incomplete'}}</span>
        </li>
      </ul>
    </div>
  </div>
</template>

<script>
import { mapMutations, mapGetters } from "vuex";

export default {
  data(){
    return {
    }
  },
  computed: mapGetters({
    todos: 'todos/todos'
  }),
  methods: {
    test() {
      console.log(this.todos)
    }
  }
};
</script>

<style>
.done {
  text-decoration: line-through;
}
.scroll-div{
  overflow: scroll;
  max-height: 500px;
}
</style>
