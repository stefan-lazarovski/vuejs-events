<script setup>
  defineProps({
    event: {
      type: Object,
      required: true,
    },
  })
</script>

<template>
  <RouterLink class="event border border-gray-800 text-slate-200 p-5 hover:border-gray-300 ease-in-out duration-500" :to="{name: 'event-details', params: {id: event.id}}">
    <div class="event-card">
      <div class="thumbnail mb-5">
        <img src="../assets/images/event3.jpg" alt="{{ event.title }}">
      </div>
      <h2 class="text-3xl mb-5">{{ event.title }}</h2>
      <span class="meta text-gray-400">@{{ event.time }} on {{ event.date }}</span>
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
  cursor: pointer;
}
</style>
