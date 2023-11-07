<template>
    <div class="chat-room">
      <message-list :messages="messages"></message-list>
      <message-input @sendMessage="handleSendMessage"></message-input>
    </div>
  </template>
  
  <script>
  import MessageList from './MessageList.vue';
  import MessageInput from './MessageInput.vue';
  
  export default {
    name: 'ChatRoom',
    components: {
      MessageList,
      MessageInput
    },
    data() {
      return {
        messages: [] // This will be replaced with actual data from your backend or Vuex store
      };
    },
    methods: {
      handleSendMessage(newMessage) {
        // Here you would handle sending the message to the backend
        const message = {
          id: this.messages.length + 1,
          text: newMessage,
          timestamp: new Date().toLocaleTimeString(),
          sender: 'You' // This would be the logged-in user in a real app
        };
        this.messages.push(message);
      }
    }
  };
  </script>
  
  <style scoped>
  .chat-room {
    display: flex;
    flex-direction: column;
    height: 100vh;
    justify-content: space-between;
  }
  </style>
  