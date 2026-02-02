<template>
  <div class="row q-col-gutter-lg">
    <div class="col-12 col-md-6">
      <q-card class="glass-card q-pa-lg">
        <div class="text-h6 text-weight-bold">Escolaridade</div>
        <q-separator dark class="q-my-md" />

        <div class="text-subtitle1 text-weight-bold">Análise e Desenvolvimento de Sistemas</div>
        <div class="text-grey-5">FATEC — Americana, SP • Ago/2019 — Ago/2022</div>

        <q-separator dark class="q-my-md" />

        <div class="text-subtitle1 text-weight-bold">Técnico em Processos de Usinagem</div>
        <div class="text-grey-5">SENAI — Santa Bárbara d’Oeste, SP • Jan/2009 — Dez/2010</div>
      </q-card>
    </div>

    <div class="col-12 col-md-6">
      <q-card class="glass-card q-pa-lg">
        <div class="text-h6 text-weight-bold">Cursos e Certificações (resumo)</div>
        <q-separator dark class="q-my-md" />

        <div class="text-grey-4">
          Cursos complementares nas áreas de programação, redes e tecnologia realizados pela Digital
          Innovation One, SENAI EAD, Fundação Bradesco e Cisco Networking Academy.
        </div>

        <div class="q-mt-md row q-gutter-sm">
          <q-chip dense outline color="primary" text-color="white">Java (DIO)</q-chip>
          <q-chip dense outline color="primary" text-color="white">Dart (DIO)</q-chip>
          <q-chip dense outline color="primary" text-color="white">Lógica (SENAI)</q-chip>
          <q-chip dense outline color="primary" text-color="white">HTML Avançado (Bradesco)</q-chip>
          <q-chip dense outline color="primary" text-color="white">ITE Essentials (Cisco)</q-chip>
          <q-chip dense outline color="primary" text-color="white">CCNA 1 e 2 (Cisco)</q-chip>
        </div>
      </q-card>
    </div>
  </div>
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
