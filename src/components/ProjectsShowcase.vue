<template>
  <div class="row q-col-gutter-lg">
    <div v-for="p in projects" :key="p.name" class="col-12 col-md-4">
      <q-card class="project-card q-pa-md" @click="open(p)">
        <div class="row items-center justify-between project-header">
          <div class="text-h6 text-weight-bold">{{ p.name }}</div>
          <q-badge color="primary" text-color="white" :label="p.type" />
        </div>

        <div class="text-grey-4 q-mt-sm">{{ p.short }}</div>

        <div class="q-mt-md row q-gutter-xs">
          <q-chip v-for="t in p.tags" :key="t" dense outline color="white" text-color="white">
            {{ t }}
          </q-chip>
        </div>

        <div class="q-mt-md row items-center justify-between text-grey-5 project-meta">
          <div><q-icon name="insights" class="q-mr-xs" />{{ p.highlight }}</div>
          <q-icon name="arrow_forward" />
        </div>
      </q-card>
    </div>
  </div>

  <q-dialog v-model="dlg">
    <q-card class="bg-grey-10 text-white project-dialog-card">
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
    name: 'Controle de Agendamento de Barbearia',
    type: 'Desktop • Java + Swing',
    short:
      'Sistema desktop para gerenciar agendamentos de barbearia, com cadastro de clientes e horários.',
    desc: 'Projeto em Java/Swing para controle de agenda de barbearia, incluindo cadastro de clientes, organização de horários e fluxo simples para uso diário no balcão.',
    highlight: 'Aplicação desktop prática',
    tags: ['Java', 'Swing', 'Desktop'],
    bullets: [
      'Cadastro e organização de clientes',
      'Controle de horários e agendamentos',
      'Interface desktop simples e objetiva',
      'Projeto acadêmico com foco em usabilidade',
    ],
    repo: 'https://github.com/lucash-c/barberShop',
    demo: '',
  },
  {
    name: 'SRF - Sistema de Referenciamento Fisioterapêutico',
    type: 'Frontend • Vue.js + Quasar',
    short:
      'Sistema de gerenciamento de dados de pacientes de Fisioterapia, criado a pedido de uma cliente de Minas Gerais.',
    desc: 'SRF (Sistema de Referenciamento Fisioterapêutico) é um sistema de interface para organizar dados de pacientes e acompanhamentos de fisioterapia, com telas e fluxos pensados para o dia a dia clínico.',
    highlight: 'UI clínica organizada',
    tags: ['Vue.js', 'Quasar', 'UI/UX', 'Formulários'],
    bullets: [
      'Cadastro e acompanhamento de pacientes',
      'Telas orientadas a fluxo clínico',
      'Componentes reutilizáveis e consistentes',
      'Foco em clareza e usabilidade no dia a dia',
    ],
    repo: 'https://github.com/lucash-c/SRF',
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
.project-dialog-card {
  width: min(92vw, 740px);
}

@media (max-width: 599px) {
  .project-card {
    padding: 16px !important;
  }
  .project-header {
    flex-direction: column;
    align-items: flex-start;
    gap: 8px;
  }
  .project-meta {
    flex-direction: column;
    align-items: flex-start;
    gap: 6px;
  }
}
</style>
