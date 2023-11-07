<template>
  <div id="app">
    <chat-room></chat-room>
  </div>
</template>

<script>
import ChatRoom from './components/ChatRoom.vue';

export default {
  name: 'App',
  components: {
    ChatRoom
  }
};
</script>

<style>
#app {
  text-align: center;
  margin-top: 60px;
}
</style>
