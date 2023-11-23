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
  <div class="page-wrapper events-page">
    <section class="page-header py-5 lg:py-[3rem]">
      <h1 class="text-center text-white-200 text-4xl font-bold mb-5 lg:mb-10">Events for Good</h1>
      <p class="text-white text-center lg:w-2/5 mx-auto">Lorem ipsum dolor sit, amet consectetur adipisicing elit. Iusto provident sit laboriosam quisquam doloribus facilis molestias optio illo molliti</p>
    </section>
    <section class="events-wrapper flex justify-between	lg:w-fit gap-5 mx-auto">
      <EventCard v-for="event in events" :key="event.id" :event="event" />
    </section>
  </div>
</template>

<style scoped lang="scss">

</style>