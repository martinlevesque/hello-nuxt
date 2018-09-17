<template>
  <section class="container">
    <div>
      <ul>
        <li v-for="item in currencies" :key="item">
          <nuxt-link class="button--green" :to="'/crypto/' + item">{{ item }}</nuxt-link>
        </li>
      </ul>
    </div>
  </section>
</template>

<script>

import axios from 'axios'

async function getTicker() {
  return await axios.get(`https://blockchain.info/ticker`);
}

async function getCurrencies() {
  const res = await getTicker();

  return Object.keys(res.data);
}

export default {
  async asyncData ({ }) {
    const currs = await getCurrencies();
    return { currencies: currs };
  },
  components: {
  }
}

</script>

<style>

</style>
