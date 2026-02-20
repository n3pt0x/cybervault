<template>
  <div class="cv-grid">
    <SectionCard
      icon="🛡"
      title="OPSEC"
      description="Operational security principles and privacy practices."
      href="/opsec/"
    />

    <SectionCard
      icon="🔎"
      title="OSINT"
      description="Open-source intelligence frameworks and investigations."
      href="/osint/"
    />

    <SectionCard
      icon="🧰"
      title="Tools"
      description="Curated cybersecurity tools categorized by use case."
      href="#"
    />

    <SectionCard
      icon="🧠"
      title="Threat Intelligence"
      description="Threat actors, TTPs, and intelligence resources."
      href="/threat-intelligence/"
    />

    <SectionCard
      icon="📚"
      title="Resources"
      description="Books, research, blogs and educational materials."
      href="/resources/"
    />
  </div>
</template>

<script setup>
import SectionCard from "./SectionCard.vue";
</script>

<style scoped>
.cv-grid {
  display: grid;
  gap: 28px;
  grid-template-columns: repeat(auto-fit, minmax(260px, 1fr));
  margin-top: 50px;
}
</style>
