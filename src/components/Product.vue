<script>
export default {
  name: "Product",
  props: {
    products: Object
  },
  data(){
    return{
      show: false,
    }
  }
}
</script>

<template>
  <v-card
      color="indigo"
      variant="tonal"
      class="mx-auto"
      max-width="300"
  >
    <v-img
        class="align-end text-white"
        height="200"
        :src="products.image"

    >

    </v-img>

    <v-card-title>
      {{products.title}}
    </v-card-title>
    <v-card-subtitle class="pt-4">
      {{products.category}}
    </v-card-subtitle>

    <v-card-text>

        <h3>Rating: {{products.rating.rate}} </h3>

    </v-card-text>

    <v-card-actions>
      <v-btn
          color="orange-lighten-2"
          variant="text"
      >
        Explore
      </v-btn>

      <v-spacer></v-spacer>

      <v-btn
          :icon="show ? 'mdi-chevron-up' : 'mdi-chevron-down'"
          @click="show = !show"
      ></v-btn>
    </v-card-actions>
    <v-expand-transition>
      <div v-show="show">
        <v-divider></v-divider>

        <v-card-text>
          <h2>{{products.title}}</h2>
          {{products.description}}
        </v-card-text>
      </div>
    </v-expand-transition>
  </v-card>
</template>

<style scoped>

</style>