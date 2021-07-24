<template>
  <v-card flat class="fill-height d-flex flex-column align-center ">
    <v-img v-if="image" width="100" aspect-ratio="1" :src="require('~/static/svg/002-struggle.svg')" />
    <v-card-title class="d-felx primary--text justify-center text-truncate">
      <h3 class="body-1">
        <slot name="title" />
      </h3>
    </v-card-title>
    <v-card-text class="text-justify">
      <slot name="defualt" />
    </v-card-text>
  </v-card>
</template>

<script>
export default {
  props: {
    image: {
      type: String, required: false, default: () => ''
    }
  }
}
</script>

<style>

</style>
