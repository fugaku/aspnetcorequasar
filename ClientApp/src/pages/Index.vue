<template>
  <div class="q-pa-md">
    <q-table
      :dense="$q.screen.lt.md"
      title="Treats"
      :data="data"
      :columns="columns"
      row-key="name"
    />
  </div>
</template>

<style>
</style>

<script>
export default {
  data () {
    return {
      columns: [
        { name: 'code', align: 'left', label: 'Code', field: 'code', sortable: true },
        {
          name: 'name',
          required: true,
          label: 'Name',
          field: 'name',
          align: 'left',
          sortable: true
        },
        { name: 'headerdetail', align: 'center', label: 'Header/Detail', field: 'headerdetail', sortable: true },
        { name: 'debitcredit', align: 'center', label: 'Debit/Credit', field: 'debitcredit', sortable: true },
        { name: 'parentcode', align: 'left', label: 'Parent Account', field: 'parentcode' }
      ],
      data: [
        {
          code: '1000.000.000',
          name: 'ASET',
          headerdetail: 'Header',
          debitcredit: 'Debit',
          parentcode: ''
        },
        {
          code: '1100.000.000',
          name: 'ASET LANCAR',
          headerdetail: 'Header',
          debitcredit: 'Debit',
          parentcode: '1000.000.000'
        },
        {
          code: '1200.000.000',
          name: 'ASET TIDAK LANCAR',
          headerdetail: 'Header',
          debitcredit: 'Debit',
          parentcode: '1000.000.000'
        }
      ]
    }
  }
}
</script>
