<template>
  <div class="chat-room flex flex-col h-[80vh] md:h-[90vh] bg-white rounded-lg shadow overflow-hidden">
    <MessageList :messages="messages" />
    <MessageInput @sendMessage="handleSendMessage" />
  </div>
</template>

<script>
import MessageList from './MessageList.vue';
import MessageInput from './MessageInput.vue';

export default {
  components: {
    MessageList,
    MessageInput
  },
  data() {
    return {
      messages: []
    };
  },
  methods: {
    handleSendMessage(newMessage) {
      this.messages.push(newMessage);
    }
  }
};
</script>
