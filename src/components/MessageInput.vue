<template>
  <div class="message-input flex-none border-t border-gray-200 p-4">
    <form @submit.prevent="send" class="flex space-x-2">
      <input 
        v-model="newMessage" 
        type="text" 
        placeholder="Type a message..." 
        class="flex-grow p-3 rounded-full border-2 border-gray-300 focus:outline-none focus:ring focus:border-gray-300"
      />
      <button 
        type="submit" 
        class="bg-blue-500 text-white rounded-full px-6 py-2 hover:bg-blue-600 focus:outline-none focus:ring-2 focus:ring-blue-500 focus:ring-opacity-50"
      >
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
        this.$emit('sendMessage', this.newMessage);
        this.newMessage = '';
      }
    }
  }
};
</script>
