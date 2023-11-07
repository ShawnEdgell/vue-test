<template>
  <div class="message-item flex flex-col items-end">
    <div class="px-4 py-2 bg-green-400 text-white rounded-t-lg rounded-l-lg">
      {{ message.content }}
    </div>
    <div class="text-xs text-gray-600 mt-1">
      {{ message.timestamp }}
    </div>
  </div>
</template>

<script>
export default {
  props: {
    message: {
      type: Object,
      required: true
    }
  }
};
</script>
