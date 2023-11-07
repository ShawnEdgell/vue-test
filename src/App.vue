<template>
  <div id="app" class="bg-gray-100 h-screen">
    <ChatRoom />
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