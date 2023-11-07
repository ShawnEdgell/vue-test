<template>
    <div class="message-input">
      <input
        type="text"
        v-model="newMessage"
        @keyup.enter="sendMessage"
        placeholder="Type a message..."
      />
      <button @click="sendMessage">Send</button>
    </div>
  </template>
  
  <script>
  export default {
    name: 'MessageInput',
    data() {
      return {
        newMessage: ''
      };
    },
    methods: {
      sendMessage() {
        if (this.newMessage.trim() === '') return;
        this.$emit('sendMessage', this.newMessage);
        this.newMessage = ''; // Clear input after sending
      }
    }
  };
  </script>
  
  <style scoped>
  .message-input {
    display: flex;
    padding: 20px;
  }
  .message-input input {
    flex-grow: 1;
    padding: 10px;
    border: 1px solid #ddd;
    border-radius: 20px;
    margin-right: 10px;
  }
  .message-input button {
    padding: 10px 20px;
    border: none;
    border-radius: 20px;
    background-color: #4caf50;
    color: white;
    cursor: pointer;
  }
  </style>
  