<template>
  <v-row>
    <v-col cols="12" align-self="center" class="text-center">
      <h2>
        {{ title }}
      </h2>
    </v-col>
    <v-col v-for="(item,index) in data" :key="index" cols="4">
      <info-box :image="item.image">
        <template #title>
          {{ item.title }}
        </template>
        <template #defualt>
          {{ item.text }}
        </template>
      </info-box>
    </v-col>
  </v-row>
</template>

<script>
export default {
  props: {
    data: {
      type: Array, required: true
    },
    title: {
      type: String, required: true
    }
  }
}
</script>

<style>

</style>
