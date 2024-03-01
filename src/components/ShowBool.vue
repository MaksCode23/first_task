<script>
import VifComponent from "@/components/VifComponent.vue";
import VshowComponent from "@/components/VshowComponent.vue";
import ToggleText from "@/components/ToggleText.vue";

export default {
  name: "ShowBool",
  components: {ToggleText, VshowComponent, VifComponent},
  data(){
    return{
      bool: true,
      checkBox: false,
    }
  },
  props:{
    selectedComponent: {},
  }

}
</script>

<template>
<div>
  <h3>Значення булевої змінної</h3>
  <h1 :class="{'green-text': bool , 'red-text': !bool}"> {{ bool }}</h1>

  <Toggle-Text :bool="bool" v-show="selectedComponent === 2"/>
  <Vshow-Component :bool="bool" v-show="selectedComponent === 3"/>
  <Vif-Component :bool="bool" v-show="selectedComponent === 4"/>

  <div class="grid-container">
    <v-btn block :disabled="checkBox" :color="bool ? 'error' : 'success'" @click="bool = !bool">{{bool ? 'FALSE' : 'TRUE'}}</v-btn>
    <v-checkbox v-model="checkBox" color="error" label="Вимкнути кнопку"></v-checkbox>
  </div>
</div>
</template>

<style scoped>
.grid-container {
  display: grid;
  grid-template-columns: repeat(2, 1fr);
}
.red-text{
  color: red;
}
.green-text{
  color: green;
}
</style>