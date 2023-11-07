<template>
  <div class="message-list flex-grow overflow-auto p-4 space-y-2">
    <MessageItem 
      v-for="message in messages" 
      :key="message.id" 
      :message="message" 
      :isCurrentUser="message.userId === currentUserId"
    />
  </div>
</template>

<script>
import MessageItem from './MessageItem.vue';

export default {
  components: {
    MessageItem
  },
  props: {
    messages: Array,
    currentUserId: String
  }
};
</script>