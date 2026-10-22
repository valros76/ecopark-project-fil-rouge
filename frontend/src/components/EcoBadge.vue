<script setup lang="ts">

import type { EcoMetrics } from '@/types/ecopark';

defineProps<{
  metrics: EcoMetrics;
}>();

</script>

<template>
  <footer v-if="metrics.responseTime" class="eco-badge">
    🌱 <strong>Sobriété Numérique (API) :</strong>
    Temps : <code>{{ metrics.responseTime }} ms</code> |
    Payload : <code>{{ metrics.payloadSize }} octets</code> |
    CO<sub>2</sub> estimé : <code>{{ metrics.co2 }} g</code>
  </footer>
</template>

<style scoped>
.eco-badge {
  margin-top: 20px;
  background: #d1e7dd;
  color: #0f5132;
  padding: 12px;
  border-radius: 8px;
  text-align: center;
  font-size: 13px;
}
</style>