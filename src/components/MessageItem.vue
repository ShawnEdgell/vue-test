<template>
    <div class="message-item" :class="{ 'sent': isSent }">
      <div class="message-content">
        <div class="message-text">{{ message.text }}</div>
        <div class="message-timestamp">{{ message.timestamp }}</div>
      </div>
    </div>
  </template>
  
  <script>
  export default {
    name: 'MessageItem',
    props: {
      message: {
        type: Object,
        required: true
      },
      isSent: {
        type: Boolean,
        default: false // This would be determined by comparing the sender with the current user
      }
    }
  };
  </script>
  
  <style scoped>
  .message-item {
    padding: 10px;
    margin-bottom: 10px;
    border-radius: 20px;
    max-width: 80%;
    align-self: flex-start;
    background-color: #f0f0f0;
  }
  .message-item.sent {
    align-self: flex-end;
    background-color: #dcf8c6;
  }
  .message-content {
    padding: 5px 10px;
    border-radius: 18px;
  }
  .message-text {
    margin: 0;
  }
  .message-timestamp {
    font-size: 0.75rem;
    text-align: right;
  }
  </style>
  