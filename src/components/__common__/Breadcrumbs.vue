<script setup>
import { defineProps } from 'vue'

defineProps({
  title: {
    type: String,
    required: true
  }
})
</script>

<template>
  <div class="breadcrumbs">
    <div class="container">
      <h2>{{ title }}</h2>

      <div class="route">
        <router-link to="/">Home</router-link>
        <i class="fi fi-rr-angle-small-right"></i>
        <span>{{ $route.name }}</span>
      </div>
    </div>
  </div>
</template>

<style scoped>
.breadcrumbs {
  height: 12rem;
  background-color: var(--bg-primary);
}

.breadcrumbs .container {
  height: 100%;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
}

.route {
  display: flex;
  align-items: center;
  color: var(--text-light);
  margin-top: 0.5rem;
}

.route i {
  position: relative;
  top: 0.2rem;
}

@media screen and (max-width: 640px) {
  .breadcrumbs {
    padding-top: 5rem;
    height: 15rem;
  }

  .route {
    font-size: 0.875rem;
  }
}
</style>
