<template>
    <div class="message-list">
      <message-item
        v-for="message in messages"
        :key="message.id"
        :message="message"
      ></message-item>
    </div>
  </template>
  
  <script>
  import MessageItem from './MessageItem.vue';
  
  export default {
    name: 'MessageList',
    components: {
      MessageItem
    },
    props: {
      messages: Array
    }
  };
  </script>
  
  <style scoped>
  .message-list {
    overflow-y: auto;
    padding: 20px;
    display: flex;
    flex-direction: column;
    align-items: flex-start;
    height: calc(100vh - 100px); /* Adjust height as per header/footer */
  }
  </style>
  