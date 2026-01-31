<template>
  <q-page class="bg-dark text-white">
    <div id="top" />

    <HeroHeader />

    <div class="container q-px-md q-pb-xl">
      <!-- SOBRE -->
      <section id="about" class="q-mt-xl">
        <SectionTitle
          kicker="QUEM SOU EU"
          title="Desenvolvedor Fullstack com foco em sistemas confiáveis e interfaces modernas."
          subtitle="Formado em ADS (FATEC Americana), com experiência em migração de sistemas legados, APIs e UI com Vue + Quasar."
        />

        <div class="row q-col-gutter-lg q-mt-md">
          <div class="col-12 col-md-7">
            <q-card class="glass-card q-pa-lg">
              <div class="text-h6 text-weight-bold">Resumo</div>
              <div class="text-grey-4 q-mt-sm">
                Sou desenvolvedor fullstack, formado em Análise e Desenvolvimento de Sistemas pela
                FATEC Americana, com facilidade em aprender novas tecnologias de forma autodidata.
                Tenho experiência prática em front-end com Vue.js e Quasar, back-end com Node.js e
                Java (Spring Boot), além de participação em migração de sistemas legados em ambiente
                corporativo. Também tenho vivência em liderança, comunicação e trabalho em equipe.
              </div>

              <div class="row q-gutter-sm q-mt-md">
                <q-chip color="primary" text-color="white" icon="bolt">Entrega consistente</q-chip>
                <q-chip color="secondary" text-color="white" icon="code">Código organizado</q-chip>
                <q-chip color="accent" text-color="white" icon="groups"
                  >Liderança comprovada</q-chip
                >
                <q-chip color="positive" text-color="white" icon="handshake"
                  >Comunicação clara</q-chip
                >
                <q-chip color="warning" text-color="black" icon="school"
                  >Aprendizado contínuo</q-chip
                >
              </div>
            </q-card>
          </div>

          <div class="col-12 col-md-5">
            <q-card class="glass-card q-pa-lg">
              <div class="text-h6 text-weight-bold">Stack</div>
              <q-separator dark class="q-my-md" />

              <div class="q-gutter-sm">
                <q-badge outline color="primary" label="Vue.js" />
                <q-badge outline color="primary" label="Quasar" />
                <q-badge outline color="primary" label="JavaScript" />
                <q-badge outline color="primary" label="Node.js" />
                <q-badge outline color="primary" label="Express" />
                <q-badge outline color="primary" label="Java" />
                <q-badge outline color="primary" label="Spring Boot" />
                <q-badge outline color="primary" label="MySQL" />
                <q-badge outline color="primary" label="MongoDB" />
                <q-badge outline color="primary" label="Git/GitHub" />
                <q-badge outline color="primary" label="REST APIs" />
                <q-badge outline color="primary" label="HTML/CSS" />
              </div>

              <q-separator dark class="q-my-md" />
              <div class="text-grey-4">
                Experiência com migração de sistemas, organização de código, boas práticas e foco em
                manutenção a longo prazo.
              </div>
            </q-card>
          </div>
        </div>
      </section>

      <!-- SKILLS -->
      <section id="skills" class="q-mt-xl">
        <SectionTitle
          kicker="HABILIDADES"
          title="O que eu entrego bem"
          subtitle="Mistura de front bonito + back sólido + maturidade de equipe e liderança."
        />
        <SkillsGrid class="q-mt-md" />
      </section>

      <!-- PROJETOS -->
      <section id="projects" class="q-mt-xl">
        <SectionTitle
          kicker="PORTFÓLIO"
          title="Projetos e cases"
          subtitle="Projetos alinhados ao que costuma ser exigido em sistemas públicos e corporativos."
        />
        <ProjectsShowcase class="q-mt-md" />
      </section>

      <!-- EXPERIÊNCIA -->
      <section id="xp" class="q-mt-xl">
        <SectionTitle
          kicker="EXPERIÊNCIA"
          title="Linha do tempo profissional"
          subtitle="Vivência real em ambiente corporativo e liderança."
        />
        <ExperienceTimeline class="q-mt-md" />
      </section>

      <!-- FORMAÇÃO -->
      <section id="edu" class="q-mt-xl">
        <SectionTitle
          kicker="FORMAÇÃO"
          title="Escolaridade e cursos"
          subtitle="Base sólida e evolução constante."
        />
        <EducationSection class="q-mt-md" />
      </section>

      <!-- CONTATO -->
      <section id="contact" class="q-mt-xl q-mb-xl">
        <ContactCTA />
      </section>
    </div>
  </q-page>
</template>

<script setup>
import HeroHeader from 'src/components/HeroHeader.vue'
import SectionTitle from 'src/components/SectionTitle.vue'
import SkillsGrid from 'src/components/SkillsGrid.vue'
import ProjectsShowcase from 'src/components/ProjectsShowcase.vue'
import ExperienceTimeline from 'src/components/ExperienceTimeline.vue'
import EducationSection from 'src/components/EducationSection.vue'
import ContactCTA from 'src/components/ContactCTA.vue'
</script>

<style scoped>
.container {
  max-width: 1100px;
  margin: 0 auto;
}
.glass-card {
  background: rgba(255, 255, 255, 0.06);
  border: 1px solid rgba(255, 255, 255, 0.08);
  backdrop-filter: blur(10px);
  border-radius: 16px;
}
</style>
