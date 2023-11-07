<template>
  <div class="chat-room flex flex-col h-full bg-gray-100 rounded-lg shadow overflow-hidden">
    <div class="flex justify-center py-4">
      <label for="toggle" class="inline-flex items-center cursor-pointer">
        <!-- switch -->
        <span class="relative">
          <span class="block w-14 h-8 bg-gray-200 rounded-full shadow-inner"></span>
          <span
            :class="currentUserId === 'user1' ? 'translate-x-0 bg-blue-500' : 'translate-x-6 bg-green-500'"
            class="absolute block w-6 h-6 mt-1 ml-1 rounded-full shadow inset-y-0 left-0 focus-within:shadow-outline transition-transform duration-300 ease-in-out"
          ></span>
        </span>
        <input id="toggle" type="checkbox" class="hidden" :checked="currentUserId === 'user2'" @change="switchUser" />
        <span class="ml-3 text-sm font-medium text-gray-900">{{ currentUserId === 'user1' ? 'User 1' : 'User 2' }}</span>
      </label>
    </div>
    <MessageList :messages="messages" :currentUserId="currentUserId" />
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
      messages: [],
      currentUserId: "user1"
    };
  },
  methods: {
    handleSendMessage(newMessageContent) {
      const newMessage = {
        content: newMessageContent,
        timestamp: new Date().toLocaleTimeString([], { hour: '2-digit', minute: '2-digit', hour12: true }),
        userId: this.currentUserId,
        color: this.currentUserId === "user1" ? "#34D399" : "#60A5FA",
        id: this.messages.length + 1
      };
      this.messages.push(newMessage);
    },
    switchUser() {
      this.currentUserId = this.currentUserId === "user1" ? "user2" : "user1";
    }
  }
};
</script>

<style>
/* Additional styles for the toggle switch */
.toggle-dot {
  top: 0.5rem;
  transition: transform 0.3s ease-in-out;
}
/* When the checkbox is checked, move the dot to the right */
input:checked ~ .toggle-dot {
  transform: translateX(1.5rem);
}
</style>
