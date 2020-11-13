<template>
  <div class="row">
    <div class="col-2 offset-xs-5">
      <h5 class="title">Tablero Kanvan</h5>
    </div>
    <div class="q-pa-md col-12">
    <q-table
      class="my-sticky-column-table"
      :data="data"
      :columns="columns"
      row-key="name"
    />
  </div>
  </div>
</template>

<script>
export default {
  name: 'PageIndex',
  data () {
    return {
      columns: [
        {
          name: 'backlog',
          label: 'No product Backlog',
          align: 'left',
          field: row => row.backlog,
          format: val => `${val}`,
          sortable: true
        },
        {
          name: 'Prioridades',
          align: 'left',
          label: 'Prioridades',
          field: 'prioridades',
          sortable: true
        },
        {
          name: 'Status',
          align: 'left',
          label: 'Status',
          field: 'status',
          sortable: true
        },
        {
          name: 'FechaStatus',
          align: 'left',
          label: 'FechaStatus',
          field: 'fechaStatus',
          sortable: true
        },
        {
          name: 'Development',
          align: 'left',
          label: 'Development',
          field: 'development',
          sortable: true
        }
      ],
      data: [
        {
          backlog: 'Gestionar proyecto',
          prioridades: 237,
          status: 'hola',
          fechaStatus: '21/05/2020',
          development: 'Fernanda Alpuche'
        },
        {
          backlog: 'Gestionar el Scrum Team',
          prioridades: 237,
          status: 'hola',
          fechaStatus: '13/11/2020',
          development: 'Carlos Arce'
        }
      ]
    }
  }
}
</script>
