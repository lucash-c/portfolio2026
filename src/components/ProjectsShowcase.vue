<template>
  <div class="row q-col-gutter-lg">
    <div v-for="p in projects" :key="p.name" class="col-12 col-md-4">
      <q-card class="project-card q-pa-md" @click="open(p)">
        <div class="row items-center justify-between">
          <div class="text-h6 text-weight-bold">{{ p.name }}</div>
          <q-badge color="primary" text-color="white" :label="p.type" />
        </div>

        <div class="text-grey-4 q-mt-sm">{{ p.short }}</div>

        <div class="q-mt-md row q-gutter-xs">
          <q-chip v-for="t in p.tags" :key="t" dense outline color="white" text-color="white">
            {{ t }}
          </q-chip>
        </div>

        <div class="q-mt-md row items-center justify-between text-grey-5">
          <div><q-icon name="insights" class="q-mr-xs" />{{ p.highlight }}</div>
          <q-icon name="arrow_forward" />
        </div>
      </q-card>
    </div>
  </div>

  <q-dialog v-model="dlg">
    <q-card class="bg-grey-10 text-white" style="min-width: 360px; max-width: 740px">
      <q-card-section class="row items-center justify-between">
        <div class="text-h6 text-weight-bold">{{ selected?.name }}</div>
        <q-btn flat round icon="close" v-close-popup />
      </q-card-section>

      <q-separator dark />

      <q-card-section class="text-grey-4">
        <div class="text-subtitle1 text-white">{{ selected?.type }}</div>
        <div class="q-mt-sm">{{ selected?.desc }}</div>

        <div class="q-mt-md">
          <div class="text-white text-weight-bold q-mb-sm">Pontos fortes</div>
          <q-list dense>
            <q-item v-for="b in selected?.bullets || []" :key="b">
              <q-item-section avatar
                ><q-icon name="check_circle" color="positive"
              /></q-item-section>
              <q-item-section>{{ b }}</q-item-section>
            </q-item>
          </q-list>
        </div>

        <div class="q-mt-md row q-gutter-sm">
          <q-btn
            v-if="selected?.repo"
            outline
            color="white"
            icon="code"
            label="GitHub"
            @click="go(selected.repo)"
          />
          <q-btn
            v-if="selected?.demo"
            color="primary"
            unelevated
            icon="open_in_new"
            label="Demo"
            @click="go(selected.demo)"
          />
        </div>

        <div class="q-mt-md text-grey-5">
          *Alguns projetos podem ser cases corporativos sem código público.
        </div>
      </q-card-section>
    </q-card>
  </q-dialog>
</template>

<script setup>
import { ref } from 'vue'

const dlg = ref(false)
const selected = ref(null)

const projects = [
  {
    name: 'Migração de Sistema Fiscal (QyonXML)',
    type: 'Corporativo • Fullstack',
    short:
      'Migração de front legado (Vaadin/Java) para Vue.js e participação em migração de back-end para Spring Boot.',
    desc: 'Participei da migração de um sistema corporativo de gerenciamento de notas fiscais. O front-end, que era em Java (Vaadin), foi migrado para JavaScript com Vue.js. Também participei da migração de uma parte do back-end que estava em Erlang, passando para Java com Spring Boot.',
    highlight: 'Migração + código corporativo',
    tags: ['Vue.js', 'Java', 'Spring Boot', 'Postman'],
    bullets: [
      'Migração de sistema legado (front)',
      'Vue.js aplicado em cenário real de empresa',
      'Participação em migração de back-end para Java + Spring Boot',
      'Uso de ferramentas: VS Code, Eclipse, Workbench, Postman',
    ],
    repo: 'https://github.com/lucash-c',
    demo: '',
  },
  {
    name: 'Dashboard Administrativo (Portfólio)',
    type: 'Frontend • Vue + Quasar',
    short: 'Interface administrativa moderna com componentes, cards, seções e navegação suave.',
    desc: 'Projeto demonstrativo de UI/UX com Quasar: layout responsivo, seções organizadas, cards, chips e navegação suave — ideal para apresentar padrão visual e organização de front-end.',
    highlight: 'UI moderna e consistente',
    tags: ['Quasar', 'Vue 3', 'UX/UI'],
    bullets: [
      'Componentização e organização de layout',
      'Responsividade (desktop e mobile)',
      'Estilo “landing page” moderno (dark + glass)',
      'Estrutura fácil de evoluir',
    ],
    repo: 'https://github.com/lucash-c',
    demo: '',
  },
  {
    name: 'Base de APIs REST (Portfólio)',
    type: 'Backend • Node/Java',
    short: 'Modelo de API REST com boas práticas e integração com front via axios.',
    desc: 'Estrutura de API REST demonstrativa para projetos: endpoints organizados, integração com front-end e base pronta para evoluir autenticação e permissões.',
    highlight: 'Integração e organização',
    tags: ['Node.js', 'Express', 'Java', 'REST'],
    bullets: [
      'Padrão de organização para rotas/serviços',
      'Integração com front usando axios',
      'Boa base para autenticação e permissões',
      'Pensado para manutenção e clareza',
    ],
    repo: 'https://github.com/lucash-c',
    demo: '',
  },
]

function open(p) {
  selected.value = p
  dlg.value = true
}

function go(url) {
  window.open(url, '_blank', 'noopener,noreferrer')
}
</script>

<style scoped>
.project-card {
  cursor: pointer;
  border-radius: 16px;
  background: linear-gradient(180deg, rgba(255, 255, 255, 0.07), rgba(255, 255, 255, 0.03));
  border: 1px solid rgba(255, 255, 255, 0.08);
  transition: transform 0.15s ease, border-color 0.15s ease;
}
.project-card:hover {
  transform: translateY(-4px);
  border-color: rgba(0, 174, 255, 0.55);
}
</style>
