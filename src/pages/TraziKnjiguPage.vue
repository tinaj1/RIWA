<template>
  <q-page class="q-pa-lg">

    <div class="text-h4 q-mb-md">
      Pretraživanje knjiga
    </div>

    <div class="text-body1 q-mb-lg">
      Unesite pojam za pretraživanje i odaberite želite li pretraživati
      prema naslovu ili autoru.
    </div>

    <q-input
      v-model="pojam"
      label="Unesite pojam"
      outlined
      class="q-mb-md"
    />

    <div class="q-mb-md">
      <q-checkbox
        v-model="pretragaNaslova"
        label="Pretraživanje prema naslovu"
      />

      <q-checkbox
        v-model="pretragaAutora"
        label="Pretraživanje prema autoru"
        class="q-ml-md"
      />
    </div>

    <q-btn
      label="Traži"
      icon="search"
      color="primary"
      @click="pretrazi"
      class="q-mb-lg"
    />

    <q-table
      title="Rezultati pretraživanja"
      :rows="rezultati"
      :columns="columns"
      row-key="id"
      flat
      bordered
    />

  </q-page>
</template>

<script setup>
import { ref } from 'vue'

const pojam = ref('')
const pretragaNaslova = ref(true)
const pretragaAutora = ref(false)

const columns = [
  {
    name: 'id',
    label: 'ID',
    field: 'id',
    align: 'left',
    sortable: true,
    style: {
      fontSize: '14px'
    },
    headerStyle: {
      fontSize: '18px'
    }
  },
  {
    name: 'naslov',
    label: 'Naslov',
    field: 'naslov',
    align: 'left',
    sortable: true,
    style: {
      fontSize: '14px'
    },
    headerStyle: {
      fontSize: '18px'
    }
  },
  {
    name: 'autor',
    label: 'Autor',
    field: 'autor',
    align: 'left',
    sortable: true,
    style: {
      fontSize: '14px'
    },
    headerStyle: {
      fontSize: '18px'
    }
  },
  {
    name: 'opis',
    label: 'Opis',
    field: 'opis',
    align: 'left',
    sortable: true,
    style: {
      fontSize: '14px'
    },
    headerStyle: {
      fontSize: '18px'
    }
  },
  {
    name: 'stanje',
    label: 'Stanje',
    field: 'stanje',
    align: 'left',
    sortable: true,
    style: {
      fontSize: '14px'
    },
    headerStyle: {
      fontSize: '18px'
    }
  }
]

const knjige = [
  {
    id: 1,
    naslov: 'The Very Hungry Caterpillar',
    autor: 'Eric Carle',
    opis: 'Klasik dječje književnosti.',
    stanje: 1
  },
  {
    id: 2,
    naslov: 'Palace of Palms',
    autor: 'Kate Teltscher',
    opis: 'Knjiga o povijesti i razvoju Kew Palms.',
    stanje: 1
  },
  {
    id: 3,
    naslov: 'How to Read a Book',
    autor: 'Mortimer J. Adler',
    opis: 'Vodič kroz umjetnost i tehnike čitanja.',
    stanje: 0
  },
  {
    id: 4,
    naslov: 'The Hobbit',
    autor: 'J. R. R. Tolkien',
    opis: 'Poznati fantastični roman.',
    stanje: 1
  }
]

const rezultati = ref(knjige)

function pretrazi() {
  const tekst = pojam.value.toLowerCase().trim()

  if (tekst === '') {
    rezultati.value = knjige
    return
  }

  rezultati.value = knjige.filter((knjiga) => {
    const naslov = knjiga.naslov.toLowerCase()
    const autor = knjiga.autor.toLowerCase()

    if (pretragaNaslova.value && pretragaAutora.value) {
      return naslov.includes(tekst) || autor.includes(tekst)
    }

    if (pretragaNaslova.value) {
      return naslov.includes(tekst)
    }

    if (pretragaAutora.value) {
      return autor.includes(tekst)
    }

    return false
  })
}
</script>