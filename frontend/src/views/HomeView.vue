<script setup lang="ts">
import SessionForm from '@/components/SessionForm.vue';
import StationList from '@/components/StationList.vue';
import { useEcoPark } from '@/composables/useEcoPark';
import { onMounted } from 'vue';

const {
  stations,
  fetchStations,
  startSession
} = useEcoPark();

const onSessionSubmit = async (
  data: {
    userName: string,
    stationId: number,
    kwhRequested: number
  }
) => {
  await startSession(
    data.userName,
    data.stationId,
    data.kwhRequested
  );
};

onMounted(() => {
  fetchStations();
});

</script>

<template>

  <SessionForm
    :stations="stations"
    @submit-session="onSessionSubmit"
  />

  <StationList
    :stations="stations"
  />

</template>
