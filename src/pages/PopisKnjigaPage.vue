<template>
  <q-page class="q-pa-lg">

    <div class="text-h4 q-mb-md">
      Popis svih knjiga
    </div>

    <div class="text-body1 q-mb-lg">
      Pregled svih knjiga koje se nalaze u knjižnici.
    </div>

    <q-table
      title="Knjige"
      :rows="knjige"
      :columns="columns"
      row-key="id"
      flat
      bordered
    />

  </q-page>
</template>

<script setup>

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
    name: 'slika',
    label: 'Slika',
    field: 'slika',
    align: 'left',
    sortable: false,
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
    slika: 'slika',
    stanje: 1
  },
  {
    id: 2,
    naslov: 'Palace of Palms',
    autor: 'Kate Teltscher',
    opis: 'Knjiga o povijesti i razvoju Kew Palms.',
    slika: 'slika',
    stanje: 1
  },
  {
    id: 3,
    naslov: 'How to Read a Book',
    autor: 'Mortimer J. Adler',
    opis: 'Vodič kroz umjetnost i tehnike čitanja.',
    slika: 'slika',
    stanje: 0
  },
  {
    id: 4,
    naslov: 'The Hobbit',
    autor: 'J. R. R. Tolkien',
    opis: 'Poznati fantastični roman.',
    slika: 'slika',
    stanje: 1
  }
]

</script>