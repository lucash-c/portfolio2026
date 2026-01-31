<template>
  <div>
    <div class="kicker text-primary text-weight-bold">{{ kicker }}</div>
    <div class="text-h5 text-weight-bolder q-mt-xs">{{ title }}</div>
    <div class="text-grey-5 q-mt-sm">{{ subtitle }}</div>
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
</style>
