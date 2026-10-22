<script setup lang="ts">
import { useEcoPark } from '@/composables/useEcoPark';

const { errorTitle, errorMessage } = useEcoPark();
</script>

<template>
  <div v-if="errorMessage" class="alert-error">
    <h3>
      🚨 {{ errorTitle }}
    </h3>
    <p>
      {{ errorMessage }}
    </p>
  </div>
</template>

<style scoped>
.alert-error {
  background: #f8d7da;
  color: #842029;
  border: 1px solid #f5c2c7;
  padding: 15px;
  border-radius: 8px;
  margin-top: 15px;
}
</style>