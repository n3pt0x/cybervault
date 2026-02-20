<template>
  <section class="cv-hero">
    <div class="cv-hero-content">
      <h1>🏛️ CyberVault</h1>
      <p class="subtitle">
        Structured cybersecurity knowledge. Centralized. Organized. Accessible.
      </p>
    </div>
  </section>
</template>

<script setup></script>

<style scoped>
.cv-hero {
  padding: 80px 20px;
  text-align: center;
  background: radial-gradient(
    circle at 50% 0%,
    rgba(37, 99, 235, 0.08),
    transparent 80%
  );
}

.cv-hero-content h1 {
  font-size: 3rem;
  font-weight: 700;
  margin-bottom: 12px;
}

.subtitle {
  font-size: 1.2rem;
  margin-bottom: 24px;
  opacity: 0.8;
}

.cv-button {
  padding: 12px 28px;
  background: #2563eb;
  color: white;
  border-radius: 8px;
  font-weight: 600;
  text-decoration: none;
  transition:
    transform 0.2s,
    box-shadow 0.2s;
}

.cv-button:hover {
  transform: translateY(-2px);
  box-shadow: 0 6px 16px rgba(37, 99, 235, 0.3);
}
</style>
