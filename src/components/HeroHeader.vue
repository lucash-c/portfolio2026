<template>
  <div class="hero">
    <div class="hero-bg" aria-hidden="true"></div>

    <div class="container q-px-md">
      <div class="row items-center q-col-gutter-xl" style="min-height: 540px">
        <div class="col-12 col-md-7">
          <div class="pill q-mb-md">
            <q-icon name="verified" class="q-mr-sm" />
          </div>

          <div class="text-h3 text-weight-bolder">
            Desenvolvedor <span class="text-primary">Fullstack</span> focado em<br />
            sistemas <span class="text-primary">confiáveis</span> e UI moderna.
          </div>

          <div class="text-subtitle1 text-grey-4 q-mt-md">
            Formado em ADS (FATEC Americana). Experiência com migração de sistemas legados,
            Vue.js/Quasar no front e Node.js/Java (Spring Boot) no back-end.
          </div>

          <div class="row q-gutter-sm q-mt-lg">
            <q-btn
              color="primary"
              unelevated
              icon="work"
              label="Ver Projetos"
              @click="scrollTo('projects')"
            />
            <q-btn outline color="white" icon="download" label="Baixar CV" @click="downloadCv()" />
            <q-btn flat icon="smart_toy" label="Pitch (30s)" @click="dialog = true" />
          </div>

          <div class="q-mt-lg text-grey-5">
            <q-icon name="location_on" class="q-mr-xs" />
            Santa Bárbara d’Oeste - SP •
            <q-icon name="mail" class="q-mx-xs" />
            lucash_c@yahoo.com.br •
            <q-icon name="call" class="q-mx-xs" />
            +55 (19) 99141-4411
          </div>

          <div class="q-mt-md row items-center q-gutter-sm social-row">
            <q-btn
              dense
              no-caps
              outline
              color="white"
              class="social-btn"
              icon="fa-brands fa-github"
              label="GitHub"
              @click="open('https://github.com/lucash-c')"
            />
            <q-btn
              dense
              no-caps
              outline
              color="white"
              class="social-btn"
              icon="fa-brands fa-linkedin"
              label="LinkedIn"
              @click="open('https://www.linkedin.com/in/lucas-henrique-de-campos-9763a7142')"
            />
          </div>
        </div>

        <div class="col-12 col-md-5">
          <div class="row justify-center q-mb-md">
            <q-avatar size="160px" class="profile-avatar">
              <img :src="profileImg" alt="Lucas Campos - Desenvolvedor Fullstack" />
            </q-avatar>
          </div>
          <q-card class="glass-card q-pa-lg">
            <div class="row items-center justify-between">
              <div class="text-h6 text-weight-bold">Destaques</div>
              <q-badge color="primary" text-color="white" label="Fullstack" />
            </div>
            <q-separator dark class="q-my-md" />

            <q-list dense class="text-grey-4">
              <q-item>
                <q-item-section avatar><q-icon name="swap_horiz" /></q-item-section>
                <q-item-section>Migração de sistema legado (Vue + Spring Boot)</q-item-section>
              </q-item>
              <q-item>
                <q-item-section avatar><q-icon name="api" /></q-item-section>
                <q-item-section>APIs REST com Node.js / Java</q-item-section>
              </q-item>
              <q-item>
                <q-item-section avatar><q-icon name="palette" /></q-item-section>
                <q-item-section>UI moderna com Vue.js + Quasar</q-item-section>
              </q-item>
              <q-item>
                <q-item-section avatar><q-icon name="groups" /></q-item-section>
                <q-item-section>Experiência em liderança e gestão de pessoas</q-item-section>
              </q-item>
            </q-list>
          </q-card>
        </div>
      </div>
    </div>

    <q-dialog v-model="dialog">
      <q-card class="bg-grey-10 text-white" style="min-width: 320px; max-width: 560px">
        <q-card-section class="row items-center justify-between">
          <div class="text-h6 text-weight-bold">Pitch (30 segundos)</div>
          <q-btn flat round icon="close" v-close-popup />
        </q-card-section>
        <q-separator dark />
        <q-card-section class="text-grey-4">
          Sou desenvolvedor fullstack, formado em ADS pela FATEC Americana, com experiência prática
          em Vue.js/Quasar, Node.js e Java com Spring Boot. Participei de migração de sistema
          corporativo legado e tenho vivência em liderança, o que ajuda muito em comunicação,
          organização e entrega em equipe. Eu foco em soluções confiáveis, fáceis de manter e com
          interface bem cuidada.
        </q-card-section>
        <q-card-actions align="right">
          <q-btn color="primary" unelevated label="Fechar" v-close-popup />
        </q-card-actions>
      </q-card>
    </q-dialog>
  </div>
</template>

<script setup>
import { ref } from 'vue'
import profileImg from 'src/assets/lucas-campos.jpg'

const dialog = ref(false)

function scrollTo(id) {
  const el = document.getElementById(id)
  if (!el) return
  el.scrollIntoView({ behavior: 'smooth', block: 'start' })
}

function downloadCv() {
  // Coloque seu PDF em /public/cv-lucas-henrique-campos.pdf
  window.open('/cv-lucas-henrique-campos.pdf', '_blank', 'noopener,noreferrer')
}

function open(url) {
  window.open(url, '_blank', 'noopener,noreferrer')
}
</script>

<style scoped>
.container {
  max-width: 1100px;
  margin: 0 auto;
}
.hero {
  position: relative;
  overflow: hidden;
  padding-top: 28px;
}
.hero-bg {
  position: absolute;
  inset: -200px -200px auto -200px;
  height: 860px;
  background: radial-gradient(600px 300px at 20% 20%, rgba(0, 174, 255, 0.35), transparent 60%),
    radial-gradient(600px 300px at 80% 30%, rgba(255, 0, 153, 0.25), transparent 60%),
    radial-gradient(700px 420px at 40% 70%, rgba(0, 255, 170, 0.18), transparent 60%),
    linear-gradient(180deg, rgba(20, 20, 24, 1), rgba(20, 20, 24, 1));
}
.pill {
  display: inline-flex;
  align-items: center;
  padding: 8px 12px;
  border-radius: 999px;
  background: rgba(255, 255, 255, 0.08);
  border: 1px solid rgba(255, 255, 255, 0.08);
}
.glass-card {
  background: rgba(255, 255, 255, 0.06);
  border: 1px solid rgba(255, 255, 255, 0.08);
  backdrop-filter: blur(10px);
  border-radius: 16px;
}
.profile-avatar {
  border: 3px solid rgba(255, 255, 255, 0.6);
  box-shadow: 0 12px 40px rgba(0, 0, 0, 0.35);
}
.profile-avatar img {
  object-fit: cover;
}
</style>
