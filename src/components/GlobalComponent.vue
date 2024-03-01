<script>
import ShowBool from "@/components/ShowBool.vue";
import VshowComponent from "@/components/VshowComponent.vue";
import VifComponent from "@/components/VifComponent.vue";
import Products from "@/components/Products.vue";
import ToggleText from "@/components/ToggleText.vue";
export default {
  name: "GlobalComponent",
  components: {
    ToggleText,
    ShowBool,
    VshowComponent,
    VifComponent,
    Products,
  },
  data(){
    return{
      bool: true,
      selectedComponent: 1,
      options: [{ text: "Axios Продукти", value: 1},
                { text: "Повідомлення", value: 2},
                { text: "V-Show компонент", value: 3},
                { text: "V-If компонент",  value: 4}],
    }
  },
}
</script>

<template>
  <div class="width">

    <v-select class="select" v-model="selectedComponent" :items="options" item-title="text" label="Виберіть компонент"/>

    <Show-Bool v-if="[2, 3, 4].includes(selectedComponent)" :selectedComponent="selectedComponent"/>
    <Products v-if="selectedComponent === 1"/>

  </div>

</template>

<style scoped>
.width{
  min-width: 400px;
  max-width: 900px;
  text-align: center;
}
.width .select{
  max-width: 400px;
  margin: 0 auto;
}

</style>