<template>
  <card-list :beers="beers" />
</template>

<script>
export default {
  async asyncData({ $axios }) {
    const beers = await $axios.$get('https://api.nuxtjs.dev/beers')
    return { beers }
  }
}
</script>