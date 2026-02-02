<template>
  <q-card class="glass-card q-pa-lg">
    <q-timeline color="primary">
      <q-timeline-entry
        title="Estagiário (Desenvolvimento)"
        subtitle="Qyon Sistemas Inteligentes"
        icon="code"
      >
        <div class="text-grey-4">
          Participação na migração do sistema QyonXML (gerenciamento de notas fiscais): front-end de
          Java (Vaadin) para JavaScript com Vue.js e parte do back-end de Erlang para Java com
          Spring Boot. Ferramentas: Eclipse, VS Code, Workbench, Postman, Notepad++.
        </div>
      </q-timeline-entry>

      <q-timeline-entry
        title="Líder de Time"
        subtitle="Hyundai Motor Brasil • Jun/2012 — Jan/2016"
        icon="groups"
      >
        <div class="text-grey-4">
          Responsável por treinar, inspirar e liderar uma equipe de 10 pessoas, garantindo
          produtividade e qualidade, com forte foco em desempenho e bom clima de equipe.
        </div>
      </q-timeline-entry>

      <q-timeline-entry
        title="Auxiliar de Escritório"
        subtitle="CFC Cillos • Jan/2012 — Jun/2012"
        icon="business_center"
      >
        <div class="text-grey-4">
          Rotina administrativa, atendimento, controle de agenda de aulas e apoio a processos
          operacionais e gerenciais.
        </div>
      </q-timeline-entry>
    </q-timeline>
  </q-card>
</template>

<style scoped>
.glass-card {
  background: rgba(255, 255, 255, 0.06);
  border: 1px solid rgba(255, 255, 255, 0.08);
  backdrop-filter: blur(10px);
  border-radius: 16px;
}

@media (max-width: 599px) {
  .glass-card {
    padding: 18px !important;
  }
}
</style>
