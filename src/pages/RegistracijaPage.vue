<template>
  <q-page class="q-pa-lg">

    <div class="text-h4 q-mb-md">
      Registracija
    </div>

    <div class="text-body1 q-mb-lg">
      Izradite korisnički račun za korištenje usluga knjižnice.
    </div>

    <q-card class="registration-card">

      <q-card-section>

        <q-input
          v-model="ime"
          label="Ime"
          outlined
          class="q-mb-md"
        />

        <q-input
          v-model="prezime"
          label="Prezime"
          outlined
          class="q-mb-md"
        />

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
          icon="person_add"
          @click="registracija"
        />

      </q-card-section>

    </q-card>

  </q-page>
</template>

<script setup>
import { ref } from 'vue'

const ime = ref('')
const prezime = ref('')
const korime = ref('')
const lozinka = ref('')

function registracija() {
  if (ime.value && prezime.value && korime.value && lozinka.value) {
    alert('Registracija je uspješno zaprimljena.')
  } else {
    alert('Molimo ispunite sva polja.')
  }
}
</script>

<style scoped>
.registration-card {
  max-width: 500px;
  width: 100%;
}
</style>