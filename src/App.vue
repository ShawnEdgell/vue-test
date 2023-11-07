<template>
  <div id="app" class="min-h-screen bg-green-100 flex justify-center items-center p-4">
    <ChatRoom class="w-full max-w-md" />
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
