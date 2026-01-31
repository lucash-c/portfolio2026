<template>
  <div class="row q-col-gutter-lg">
    <div v-for="s in skills" :key="s.title" class="col-12 col-md-6">
      <q-card class="glass-card q-pa-lg">
        <div class="row items-center no-wrap">
          <q-avatar size="42px" class="bg-primary text-white">
            <q-icon :name="s.icon" />
          </q-avatar>
          <div class="q-ml-md">
            <div class="text-h6 text-weight-bold">{{ s.title }}</div>
            <div class="text-grey-5">{{ s.subtitle }}</div>
          </div>
        </div>

        <div class="text-grey-4 q-mt-md">{{ s.desc }}</div>

        <div class="q-mt-md row q-gutter-sm">
          <q-chip v-for="t in s.tags" :key="t" dense outline color="primary" text-color="white">
            {{ t }}
          </q-chip>
        </div>
      </q-card>
    </div>
  </div>
</template>

<script setup>
const skills = [
  {
    icon: 'dashboard_customize',
    title: 'Frontend',
    subtitle: 'Interfaces modernas e funcionais',
    desc: 'Desenvolvimento de interfaces com foco em usabilidade, responsividade e organização de componentes.',
    tags: ['Vue.js', 'Quasar', 'React.js', 'HTML5', 'CSS3', 'JavaScript'],
  },
  {
    icon: 'api',
    title: 'Backend',
    subtitle: 'APIs e regras de negócio',
    desc: 'Criação e manutenção de APIs REST, autenticação e integração entre sistemas.',
    tags: ['Node.js', 'Express', 'Java', 'Spring Boot', 'REST', 'Postman'],
  },
  {
    icon: 'storage',
    title: 'Banco de Dados',
    subtitle: 'Modelagem e persistência',
    desc: 'Modelagem básica, consultas e integração com aplicações.',
    tags: ['MySQL', 'MongoDB', 'SQL'],
  },
  {
    icon: 'groups',
    title: 'Liderança e Comunicação',
    subtitle: 'Experiência comprovada',
    desc: 'Vivência em liderança e gestão de pessoas, com foco em performance, qualidade e bom clima de equipe.',
    tags: ['Liderança', 'Comunicação', 'Gestão de pessoas', 'Resolução de problemas'],
  },
]
</script>

<style scoped>
.glass-card {
  background: rgba(255, 255, 255, 0.06);
  border: 1px solid rgba(255, 255, 255, 0.08);
  backdrop-filter: blur(10px);
  border-radius: 16px;
}
</style>
