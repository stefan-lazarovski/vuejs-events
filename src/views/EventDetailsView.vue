<script setup>
import { onMounted, ref } from 'vue'
import EventService from '@/services/EventService.js';

const props = defineProps({
    id: {
        required: true,
    },
});
const event = ref(null);

onMounted(() => {
  EventService.getEvent(props.id).then((response) => {
    event.value = response.data
  }).catch((error) => {
    console.log(error);
  })
})
</script>

<template>
    <div id="event-detail" v-if="event">
        <h1>{{ event.title }}</h1>
        <p>{{ event.time }} on {{ event.date }} @ {{ event.location }}</p>
        <p class="meta">{{ event.description }}</p>
    </div>
</template>