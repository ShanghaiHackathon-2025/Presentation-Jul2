<template>
  <div class="container">
    <!-- Topic Section -->
    <div class="topic">
      <h2>{{ topic }}</h2>
    </div>

    <!-- Message Content -->
    <div class="messages" ref="messageContainer">
      <slot></slot> <!-- Slot for dynamic content -->
    </div>
  </div>
</template>

<script setup>
import { nextTick, onUpdated, ref } from 'vue';

const messageContainer = ref(null);

// Automatically scroll to the bottom after content is added
onUpdated(() => {
  nextTick(() => {
    const container = messageContainer.value;
    if (container) {
      container.scrollTop = container.scrollHeight;
    }
  });
});

// Define the topic prop
defineProps({
  topic: {
    type: String,
    required: true,
  },
});
</script>

<style scoped>
/* Container for the entire component */
.container {
  width: 100%;
  height: clamp(200px, 30vh, 400px); /* Adjust the height based on your needs */
  display: flex;
  flex-direction: column;
  border: 1px solid #ccc;
  border-radius: 8px;
  margin-top: 8px;
}

/* Topic title section */
.topic {
  padding: 8px 12px;
  background-color: #f9f9f9; /* Similar to light background */
  border-bottom: 1px solid #ddd;
  font-size: 18px;
  font-weight: bold;
}

/* Messages container */
.messages {
  flex-grow: 1;
  overflow-y: auto;
  padding: 16px;
  display: flex;
  flex-direction: column;
  max-height: 100%;
  font-size: 0.75em;
}

/* Individual message style */
.message {
  margin-bottom: 10px;
  padding: 12px;
  background-color: #fafafa;
  border-radius: 6px;
  border: 1px solid #e0e0e0;
}

/* Style for the topic title */
h2 {
  margin: 0;
  font-size: 1.2rem;
  font-weight: 600;
  color: #333; /* Subtle, not too bold */
}
</style>
