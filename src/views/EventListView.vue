<script setup>
import { ref, onMounted } from 'vue'
import EventService from '@/services/EventService.js'
import EventCard from '@/components/EventCard.vue'

const events = ref(null);

onMounted(() => {
  EventService.getEvents().then((response) => {
    events.value = response.data
  }).catch((error) => {
    console.log(error);
  })
})
</script>

<template>
  <h1 class="text-center">Events for Good</h1>
  <div id="home" class="events-wrapper">
    <EventCard v-for="event in events" :key="event.id" :event="event" />
  </div>
</template>

<style scoped lang="scss">
.events-wrapper {
  display: flex;
  flex-direction: column;
  align-items: center;
  .event-card {
    width: fit-content;
  }
}
</style>