<template>
  <div class="message-input flex-none border-t border-gray-200 p-4">
    <form @submit.prevent="send" class="flex space-x-2">
      <input v-model="newMessage" type="text" placeholder="Type a message..." class="flex-grow p-3 rounded-full border-2 border-green-500 focus:outline-none focus:ring focus:border-green-300" />
      <button type="submit" class="bg-green-500 text-white rounded-full px-6 py-2 hover:bg-green-600 focus:outline-none focus:ring-2 focus:ring-green-500 focus:ring-opacity-50">
        Send
      </button>
    </form>
  </div>
</template>

<script>
export default {
  data() {
    return {
      newMessage: ''
    };
  },
  methods: {
    send() {
      if (this.newMessage.trim()) {
        const newMessage = {
          content: this.newMessage,
          timestamp: new Date().toLocaleTimeString([], { hour: '2-digit', minute: '2-digit', hour12: true }),
          id: Date.now()
        };
        this.$emit('sendMessage', newMessage);
        this.newMessage = '';
      }
    }
  }
};
</script>
