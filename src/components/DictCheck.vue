<template>
  <div class="dictcheck">

      <button @click="getWords">Get Words</button>
      <h1>{{ data }}</h1>
    <p>sexy.</p>
  </div>

</template>

<script>

export default {
  data() {
    return {
      data: []
    }
  },
  methods: {
    async getWords() {
      let url = 'https://dictionary.jasmes.workers.dev/'
      let response = await fetch(url, {
        method: 'GET',
        headers: {
          'Content-Type': 'application/json',
          'Access-Control-Allow-Origin': '*',
          'Access-Control-Allow-Methods': 'GET, POST, PUT, DELETE, OPTIONS',
          'Access-Control-Allow-Headers': 'Content-Type, Access-Control-Allow-Headers, Authorization, X-Requested-With',
          'Access-Control-Max-Age': '86400'
        }
      })
      .then(res => res.json())
      .then (data => {
        this.data = data
      })


    }
  },
  name: "dictcheck"
}


</script>

<style scoped>
h1 {
  position: static;
  color: red;
}
</style>
