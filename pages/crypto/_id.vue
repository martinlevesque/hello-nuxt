<template>
  <section class="container">
    <div>
      <h2>1 BTC = {{ price.last }} {{ price.symbol }} </h2>
    </div>
  </section>
</template>

<script>

import axios from 'axios'

async function getTicker() {
  return await axios.get(`https://blockchain.info/ticker`);
}

export default {
  async asyncData ({ params }) {
    const ticker = await getTicker();
    return { price: ticker.data[params.id] };
  },
  components: {
  }
}

</script>

<style>

</style>
gitlab-ncsa.ubisoft.org  hello-nuxt  install-amber  mtl-go2-devops  openode-www  poc-chat-amber  traceify  traceify-node  vue-ssr
