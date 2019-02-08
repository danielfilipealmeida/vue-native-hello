<template>
  <app-navigation></app-navigation>
</template>

<script>
import { StackNavigator } from "vue-native-router";
import HomeScreen from "./src/screens/homeScreen.vue";
import CatalogueScreen from "./src/screens/catalogueScreen.vue";
import productDetailScreen from "./src/screens/productDetailScreen.vue";
import Vuex from "vuex";
import Vue from "vue-native-core";

Vue.use(Vuex);

const store = new Vuex.Store({
  state: {
    count: 1
  },
  mutations: {
    increment(state) {
      state.count++;
    }
  }
});
const AppNavigation = StackNavigator(
  {
    Home: HomeScreen,
    Catalogue: CatalogueScreen,
    ProductDetail: productDetailScreen
  },
  {
    initialRouteName: "Home"
  }
);
export default {
  components: { AppNavigation },
  store:store
};
</script>

<style>
</style>