<template>
  <a :href="href" class="cv-card">
    <div class="cv-card-icon">{{ icon }}</div>
    <div class="cv-card-content">
      <h3>{{ title }}</h3>
      <p>{{ description }}</p>
    </div>
  </a>
</template>

<script setup>
defineProps({
  title: String,
  description: String,
  href: String,
  icon: String
})
</script>

<style scoped>
.cv-card {
  display: flex;
  gap: 16px;
  padding: 22px;
  border-radius: 16px;
  border: 1px solid rgba(148, 163, 184, 0.15);
  background: rgba(15, 23, 42, 0.55);
  backdrop-filter: blur(12px);
  text-decoration: none;
  transition: all 0.3s ease;
}

.cv-card:hover {
  border-color: #2563eb;
  transform: translateY(-6px) scale(1.04);
  box-shadow: 0 14px 36px rgba(37, 99, 235, 0.25);
}

.cv-card-icon {
  font-size: 30px;
  display: flex;
  align-items: center;
}

.cv-card-content h3 {
  margin: 0;
  font-size: 18px;
}

.cv-card-content p {
  margin: 6px 0 0;
  font-size: 14px;
  opacity: 0.75;
}
</style>