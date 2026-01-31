<template>
  <q-layout view="lHh Lpr lFf" class="bg-dark text-white">
    <q-header elevated class="glass">
      <q-toolbar class="q-px-md">
          <q-btn flat round icon="business_center" aria-label="Logo" @click="scrollTo('top')" />
        <q-toolbar-title class="text-weight-bold site-title">
          Lucas Henrique Campos <span class="text-primary">• Fullstack</span>
        </q-toolbar-title>

        <div class="gt-sm row items-center q-gutter-sm">
          <q-btn flat dense label="Sobre" @click="scrollTo('about')" />
          <q-btn flat dense label="Skills" @click="scrollTo('skills')" />
          <q-btn flat dense label="Projetos" @click="scrollTo('projects')" />
          <q-btn flat dense label="Experiência" @click="scrollTo('xp')" />
          <q-btn flat dense label="Formação" @click="scrollTo('edu')" />
          <q-btn color="primary" unelevated label="Contato" @click="scrollTo('contact')" />
        </div>

        <q-btn class="lt-md" flat round icon="menu" @click="drawer = true" />
      </q-toolbar>
    </q-header>

    <q-drawer v-model="drawer" side="right" overlay bordered class="bg-grey-10 text-white">
      <q-list padding>
        <q-item clickable v-ripple @click="nav('about')"
          ><q-item-section>Sobre</q-item-section></q-item
        >
        <q-item clickable v-ripple @click="nav('skills')"
          ><q-item-section>Skills</q-item-section></q-item
        >
        <q-item clickable v-ripple @click="nav('projects')"
          ><q-item-section>Projetos</q-item-section></q-item
        >
        <q-item clickable v-ripple @click="nav('xp')"
          ><q-item-section>Experiência</q-item-section></q-item
        >
        <q-item clickable v-ripple @click="nav('edu')"
          ><q-item-section>Formação</q-item-section></q-item
        >
        <q-item clickable v-ripple @click="nav('contact')"
          ><q-item-section>Contato</q-item-section></q-item
        >
      </q-list>
    </q-drawer>

    <q-page-container>
      <router-view />
    </q-page-container>

    <q-footer class="bg-grey-10 text-grey-4">
      <div class="q-pa-md row items-center justify-between">
        <div>© {{ new Date().getFullYear() }} Lucas Henrique Campos</div>
        <div class="row items-center q-gutter-sm">
          <q-btn flat round icon="email" @click="open('mailto:lucash_c@yahoo.com.br')" />
        </div>
      </div>
    </q-footer>
  </q-layout>
</template>

<script setup>
import { ref } from 'vue'

const drawer = ref(false)

function scrollTo(id) {
  const el = document.getElementById(id)
  if (!el) return
  el.scrollIntoView({ behavior: 'smooth', block: 'start' })
}

function nav(id) {
  drawer.value = false
  setTimeout(() => scrollTo(id), 150)
}

function open(url) {
  window.open(url, '_blank', 'noopener,noreferrer')
}
</script>

<style scoped>
.glass {
  background: rgba(20, 20, 24, 0.6);
  backdrop-filter: blur(10px);
  border-bottom: 1px solid rgba(255, 255, 255, 0.08);
}
.site-title {
  font-size: 1rem;
}
@media (min-width: 600px) {
  .site-title {
    font-size: 1.25rem;
  }
}
</style>
