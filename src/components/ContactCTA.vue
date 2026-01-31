<template>
  <q-card class="cta q-pa-lg">
    <div class="row items-start q-col-gutter-xl">
      <div class="col-12 col-md-6">
        <div class="text-h5 text-weight-bolder">Contato</div>
        <div class="text-grey-4 q-mt-sm">
          Se você busca um fullstack com experiência real, foco em manutenção e boa comunicação,
          vamos conversar.
        </div>

        <div class="q-mt-md text-grey-4">
          <div><q-icon name="mail" class="q-mr-sm" /> lucash_c@yahoo.com.br</div>
          <div class="q-mt-sm"><q-icon name="call" class="q-mr-sm" /> +55 (19) 99141-4411</div>
          <div class="q-mt-sm">
            <q-icon name="location_on" class="q-mr-sm" /> Santa Bárbara d’Oeste - SP
          </div>
        </div>

        <div class="row q-gutter-sm q-mt-lg">
          <q-btn color="primary" unelevated icon="email" label="Enviar e-mail" @click="mailto()" />
          <q-btn
            outline
            color="white"
            icon="code"
            label="GitHub"
            @click="open('https://github.com/lucash-c')"
          />
          <q-btn
            outline
            color="white"
            icon="linkedin"
            label="LinkedIn"
            @click="open('https://www.linkedin.com/in/lucas-henrique-de-campos-9763a7142')"
          />
        </div>

        <div class="q-mt-md text-grey-5">
          *Facebook eu deixei fora do portfólio por ser um canal mais pessoal.
        </div>
      </div>

      <div class="col-12 col-md-6">
        <q-input v-model="name" label="Seu nome" dark filled />
        <q-input v-model="msg" label="Mensagem" type="textarea" dark filled class="q-mt-md" />
        <q-btn
          class="q-mt-md"
          color="primary"
          unelevated
          icon="send"
          label="Gerar e-mail"
          @click="mailto(true)"
        />
        <div class="text-grey-5 q-mt-sm">(Abre seu app de e-mail já com o texto pronto.)</div>
      </div>
    </div>
  </q-card>
</template>

<script setup>
import { ref } from 'vue'

const name = ref('')
const msg = ref('')

function open(url) {
  window.open(url, '_blank', 'noopener,noreferrer')
}

function mailto(withTemplate = false) {
  const to = 'lucash_c@yahoo.com.br'
  const subject = encodeURIComponent('Contato via Portfólio')
  const body = withTemplate
    ? encodeURIComponent(
        `Olá Lucas! Aqui é ${name.value || '[seu nome]'}.\n\n${
          msg.value || 'Quero conversar sobre uma oportunidade.'
        }\n\nObrigado!`
      )
    : encodeURIComponent('Olá Lucas! Quero conversar sobre uma oportunidade.')
  window.location.href = `mailto:${to}?subject=${subject}&body=${body}`
}
</script>

<style scoped>
.cta {
  border-radius: 18px;
  background: radial-gradient(600px 240px at 20% 20%, rgba(0, 174, 255, 0.28), transparent 60%),
    radial-gradient(600px 240px at 80% 20%, rgba(255, 0, 153, 0.2), transparent 60%),
    linear-gradient(180deg, rgba(255, 255, 255, 0.08), rgba(255, 255, 255, 0.04));
  border: 1px solid rgba(255, 255, 255, 0.1);
}
</style>
