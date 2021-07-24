<template>
  <v-row>
    <v-col cols="12">
      <InfoRow :title="info[0].title" :data="info[0].data" />
    </v-col>
    <v-col cols="12">
      <WeLoveYouWin />
    </v-col>
  </v-row>
</template>

<script>
export default {
  async asyncData ({ $content }) {
    const info = await $content('home').fetch()
    console.log({ info })
    return {
      info
    }
  }
}
</script>

<style>

</style>
