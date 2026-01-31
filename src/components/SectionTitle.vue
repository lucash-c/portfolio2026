<template>
  <div>
    <div class="kicker text-primary text-weight-bold">{{ kicker }}</div>
    <div class="section-title text-weight-bolder q-mt-xs">{{ title }}</div>
    <div class="section-subtitle text-grey-5 q-mt-sm">{{ subtitle }}</div>
  </div>
</template>

<script setup>
defineProps({
  kicker: String,
  title: String,
  subtitle: String,
})
</script>

<style scoped>
.kicker {
  letter-spacing: 0.12em;
  font-size: 12px;
}
.section-title {
  font-size: clamp(1.4rem, 5vw, 2rem);
  line-height: 1.3;
}
.section-subtitle {
  font-size: 0.98rem;
  line-height: 1.6;
}
</style>
