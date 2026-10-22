<script setup lang="ts">
import { RouterView } from 'vue-router'
import MainHead from './layouts/MainHead.vue';
import ErrorBanner from './layouts/ErrorBanner.vue';
import { useEcoPark } from './composables/useEcoPark.ts';

const {ecoMetrics} = useEcoPark();
</script>

<template>
  <div class="container">
    <MainHead />
    <ErrorBanner />
    <main class="grid">
      <RouterView />
    </main>

    <EcoBadge :metrics="ecoMetrics"/>
  </div>
</template>

<style scoped>
.container {
  max-width: 900px;
  margin: 0 auto;
  padding: 20px;
  font-family: system-ui, sans-serif;
}

.grid {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 20px;
  margin-top: 20px;
}
</style>
