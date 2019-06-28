<template>
  <q-page class="flex">
    <div class="q-pa-md">
      <div class="row">
        <div class="column">
          <q-btn color="primary" label="Call" @click="call"/>
        </div>
      </div>
      <div class="row">
        <div class="column">
          <q-list border separator>
            <q-item v-for="(item, index) in items" :key="index">
              <q-item-section>{{ item.summary }}</q-item-section>
            </q-item>
          </q-list>
        </div>
      </div>
    </div>
  </q-page>
</template>

<style>
</style>

<script>
export default {
  name: 'PageIndex',
  data: function () {
    return {
      items: []
    }
  },
  methods: {
    call: function () {
      this.$axios.get('/api/sampledata/weatherforecasts').then(response => {
        this.items = response.data
      })
    }
  }
}
</script>
