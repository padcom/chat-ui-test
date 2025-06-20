<template>
  <Chat>
    <Messages v-slot="{ message }" :messages>
      <Message :message class="markdown-body" />
    </Messages>
    <Prompt />
  </Chat>
</template>

<script setup>
import { ref } from 'vue'
import { Chat, Messages, Message, Prompt } from '@padcom/chat-ui'
import '@padcom/chat-ui-formatter-marked'

const messages = ref([
  { role: 'system', content: 'You are a helpful assistant using [LM Studio](https://lmstudio.ai)' },
  { role: 'user', content: 'Who are you?' },
  { role: 'assistant', content: 'I am your *faithful* AI assistant' },
  { role: 'xxx', content: 'This is an example custom message' },
  { role: 'user', content: 'Who are you?' },
  { role: 'error', content: 'Error: connection refused' },
  { role: 'user', content: 'Who are you?' },
  { role: 'assistant', content: 'I am your **faithful** AI assistant' },
  { role: 'user', content: 'Who are you?' },
  { role: 'assistant', content: 'I am your _faithful_ AI assistant' },
])
</script>

<style>
html, body {
  margin: 0;
  padding: 0;

}
</style>

<style scoped>
.chat {
  max-width: 50%;
  margin-inline: auto;
  padding-block: 1rem;
  height: calc(100dvh - 2rem);
}
</style>
