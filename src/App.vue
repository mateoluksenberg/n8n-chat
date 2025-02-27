<!-- App.vue -->
<script setup>
import { onMounted } from 'vue';
import '@n8n/chat/style.css';
import { createChat } from '@n8n/chat';

onMounted(() => {
  createChat({
    webhookUrl: 'https://mateoluksenberg.app.n8n.cloud/webhook/15e4d662-3f98-48d0-9f50-68838769ecac/chat',
    mode: 'fullscreen',
    target: '#n8n-chat',
    showWelcomeScreen: true,
    defaultLanguage: 'es',
    initialMessages: [
      'Hola! 👋',
      'Soy el asistente IA de la UB, ¿como te puedo ayudar?'
    ],
    i18n: {
      es: {
        title: 'UB',
        subtitle: "Asistente Virtual de la Universidad de Belgrano",
        footer: ' ',
        getStarted: '¡¡Empezar!!',
        inputPlaceholder: 'Escribir..'
      }
    }
  });
});
</script>

<template>
  <div id="n8n-chat"></div>
</template>

<style>
:root {
  --chat--header--background: #A52A2A; /* Red-brown header background */
  --chat--header--color: #ffffff;        /* White header text */
}

/* Center the chat container */
#n8n-chat {
  position: fixed;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  width: 1500px;
  height: 700px;
  z-index: 9999;
  box-shadow: 0 2px 8px rgba(194, 19, 19, 0.3);
  border-radius: 8px;
  overflow: hidden;
}

/* Override the default logo in the chat header with your custom logo */
.n8n-chat-logo {
  background: url(~@/assets/logo.png) no-repeat center;
  background-size: contain;
  width: 50px;
  height: 50px;
}

/* Override the chat window background to be dark red */
.n8n-chat-window {
  background-color: #8B0000 !important;
}

/* Hide the "Powered by n8n" element */
.n8n-chat-poweredby {
  display: none;
}
</style>
