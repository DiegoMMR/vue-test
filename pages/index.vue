<template>
  <div class="container">
    <Dialog  />
    <Todos />
  </div>
</template>

<script>
import Logo from "../components/Logo.vue";
import Dialog from "../components/Dialog.vue";
import Todos from "../components/Todos.vue";
import { mapState } from 'vuex'

export default {
  components: {
    Logo,
    Dialog,
    Todos,
  }
};
</script>

<style>
@import url('https://stackpath.bootstrapcdn.com/bootstrap/4.3.1/css/bootstrap.min.css');
</style>
