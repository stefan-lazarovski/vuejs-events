<script setup>
  defineProps({
    event: {
      type: Object,
      required: true,
    },
  })
</script>

<template>
  <RouterLink class="event" :to="{name: 'event-details', params: {id: event.id}}">
    <div class="event-card">
      <h2>{{ event.title }}</h2>
      <span class="meta">@{{ event.time }} on {{ event.date }}</span>
    </div>
  </RouterLink>
</template>

<style scoped>
h1 {
  font-weight: 500;
  font-size: 2.6rem;
  position: relative;
  top: -10px;
}

h3 {
  font-size: 1.2rem;
}
.event-card {
  padding: max(0.5rem, 2vw);
  cursor: pointer;
  border: 1px solid #d9d9d9;
  margin-bottom: 2rem;
}
</style>
