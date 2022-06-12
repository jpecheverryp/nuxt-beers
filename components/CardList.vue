<template>
  <ul class="flex flex-wrap gap-6 justify-center">
    <li v-for="beer in beers">
      <card :beer="beer" />
    </li>
  </ul>
</template>

<script>
export default {
  props: ['beers']
}
</script>
