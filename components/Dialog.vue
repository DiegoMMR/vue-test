<template>
  <div class="dialog">
    <div class="text-center">
      <button @click="save_data" class="do something btn btn-success">do something!</button>
    </div>
    <p class="primary-text">- Omae wa Mou Shindeiru.</p>
    <p class="response-text" v-show="show">-</p>
  </div>
</template>

<script>
import { mapMutations, mapGetters } from 'vuex'
import axios from 'axios'

export default {
  props: ['text'],
  data() {
    return {
      loaded: false,
      show: false,
      rows: []
    }
  },
  watch:{
  },
  methods: {
    save_data() { 
      axios.get('https://jsonplaceholder.typicode.com/todos').then(response => {
        console.log(response);
        this.$store.commit('todos/todos', response.data)
      });

    },
    do_some() {
      //this.loaded = false;
      var request = new XMLHttpRequest();
      request.open('GET', 'https://jsonplaceholder.typicode.com/todos', true)
      request.onload = function() {
       var data = JSON.parse(this.response)

        if (request.status >= 200 && request.status < 400) {
          this.rows = data;
          console.log(this.rows, 'data1')
          return true;
        } else {
          return true;
        }
      }

      request.send()
         
    }
  }
};
</script>