<template>
  <div class="message-container agent-message">
    <div class="message-label">{{ agent }}</div>
    <div class="message-content">
      <slot></slot>
    </div>
  </div>
</template>

<script setup>
import { defineProps } from 'vue';

const props = defineProps({
  agent: {
    type: String,
    default: 'Agent',
  },
});
</script>

<style scoped>
/* Base message container styles - same as UserPrompt for consistency */
.message-container {
  margin-bottom: 20px;
  font-family: 'Inter', system-ui, -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, Oxygen, Ubuntu, Cantarell, "Open Sans", "Helvetica Neue", sans-serif;
  line-height: 1.6;
}

/* Labels - same as UserPrompt */
.message-label {
    margin-bottom: 8px;
    font-weight: 600;
    margin-right: 15px;
    min-width: 60px;
    text-align: right;
    color: #555;
    font-size: 0.9em;
    padding-top: 5px;
}

/* Content bubbles - same as UserPrompt */
.message-content {
  flex-grow: 1;
  padding: 12px 18px;
  border-radius: 8px;
  background-color: #f8f8f8;
  color: #333;
  box-shadow: 0 1px 3px rgba(0, 0, 0, 0.04);
  border: 1px solid #eee;
}

/* Agent specific styles - similar to user, but distinct */
.agent-message .message-content {
  background-color: #ffffff; /* Pure white for agent, often seen in clean UIs */
  border-color: #f0f0f0; /* Very light border */
}
</style>