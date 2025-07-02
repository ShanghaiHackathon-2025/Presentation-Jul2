<template>
  <div class="message-container user-message">
    <div class="message-label">User</div>
    <div class="message-content">
      <slot></slot>
    </div>
  </div>
</template>

<style scoped>
/* Base message container styles, keeping it clean */
.message-container {
  display: flex;
  flex-direction: column;
  align-items: flex-start;
  margin-bottom: 20px;
  /* Using consistent spacing with apple-basic's general feel */
  font-family: 'Inter', system-ui, -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, Oxygen, Ubuntu, Cantarell, "Open Sans", "Helvetica Neue", sans-serif;
  line-height: 1.6; /* Slightly more relaxed line height */
}

/* Labels - simple and understated */
.message-label {
  font-weight: 600; /* Slightly bolder, but not too heavy */
  margin-right: 15px;
  min-width: 60px;
  text-align: left;
  margin-bottom: 8px;
  color: #555; /* Muted dark grey for labels */
  font-size: 0.9em; /* Slightly smaller to feel less dominant */
  padding-top: 5px; /* Align text better with the bubble content */
}

/* Content bubbles - clean, subtle backgrounds, no harsh borders */
.message-content {
  flex-grow: 1;
  padding: 12px 18px; /* A bit more padding for a softer look */
  border-radius: 8px; /* Softly rounded corners */
  background-color: #f8f8f8; /* Very light grey, almost white */
  color: #333; /* Soft black for main text */
  box-shadow: 0 1px 3px rgba(0, 0, 0, 0.04); /* Very subtle shadow */
  border: 1px solid #eee; /* Light, almost invisible border */
}

/* User specific styles - slightly different shade */
.user-message .message-content {
  background-color: #f0f0f0; /* A touch darker grey for user, still light */
  border-color: #e0e0e0; /* Matches the slightly darker background */
}
</style>