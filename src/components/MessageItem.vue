<template>
  <div class="flex w-full" :class="{ 'justify-end': isCurrentUser, 'justify-start': !isCurrentUser }">
    <div :class="{ 'max-w-xs': !isCurrentUser, 'max-w-md': isCurrentUser }">
      <div :class="messageBubbleClasses">
        {{ message.content }}
      </div>
      <div class="text-xs mt-1" :class="{ 'text-right': isCurrentUser, 'text-left': !isCurrentUser }">
        {{ message.timestamp }}
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    message: {
      type: Object,
      required: true
    },
    isCurrentUser: {
      type: Boolean,
      default: false
    }
  },
  computed: {
    messageBubbleClasses() {
      return [
        'px-4 py-2 rounded-lg shadow',
        {
          'bg-blue-500 text-white rounded-br-none': this.isCurrentUser, // Blue background for current user
          'bg-gray-300 text-gray-700 rounded-bl-none': !this.isCurrentUser, // Grey background for other users
          'text-right': this.isCurrentUser,
          'text-left': !this.isCurrentUser
        }
      ];
    }
  }
};
</script>
