<template>
  <q-page class="q-pa-lg">

    <div class="text-h4 q-mb-md">
      Login
    </div>

    <div class="text-body1 q-mb-lg">
      Prijavite se u sustav knjižnice.
    </div>

    <q-card class="login-card">

      <q-card-section>

        <q-input
          v-model="korime"
          label="Korisničko ime"
          outlined
          class="q-mb-md"
        />

        <q-input
          v-model="lozinka"
          label="Lozinka"
          type="password"
          outlined
          class="q-mb-md"
        />

        <q-btn
          label="Potvrdi"
          color="primary"
          icon="login"
          @click="prijava"
        />

      </q-card-section>

    </q-card>

  </q-page>
</template>

<script setup>
import { ref } from 'vue'

const korime = ref('')
const lozinka = ref('')

function prijava() {
  if (korime.value && lozinka.value) {
    alert('Podaci za prijavu su uneseni.')
  } else {
    alert('Molimo unesite korisničko ime i lozinku.')
  }
}
</script>

<style scoped>
.login-card {
  max-width: 500px;
  width: 100%;
}
</style>