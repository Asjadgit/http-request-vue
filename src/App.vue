<template>
    <!-- <UpdateRequest /> -->
    <GetRequest />
    <!-- <PostRequest /> -->
</template>

<script>
// import UpdateRequest from './components/UpdateRequest.vue';
import GetRequest from './components/GetRequest.vue'
// import PostRequest from './components/PostRequest.vue'
export default {
  name: 'App',
  components: {
    GetRequest
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
