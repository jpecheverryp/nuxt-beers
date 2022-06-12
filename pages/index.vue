<template>
  <div>
    <Hero />
    <h2 class="text-2xl text-center my-3">Look at all those Beers</h2>
    <card-list :beers="beers" />
    <!-- <pre>{{ beers }}</pre> -->
  </div>
</template>

<script>


export default {
  name: 'IndexPage',
  async asyncData({ $axios }) {
    const beers = await $axios.$get('https://api.nuxtjs.dev/beers')
    return { beers }
  }
}
</script>
