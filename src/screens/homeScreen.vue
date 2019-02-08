<template>
  <view class="container">
    <text class="text-color-primary">{{message}}</text>
    <button :on-press="onButtonPress" title="Go to Catalogue"/>
    <text>{{count}}</text>
     <button :on-press="increment" title="Increment"/>
  </view>
</template>

<script>
export default {
  props: {
    navigation: {
      type: Object
    },
    store: {
        type: Object
    }
  },
  methods: {
    onButtonPress: function() {
      this.navigation.navigate("Catalogue");
    },
    increment: function() {
        this.$store.commit('increment');
    }
  },
  data: function() {
    return {
      message: "Home screen",
    };
  },
  computed: {
      count: function() {
          return this.$store.state.count;
      }
  }
};
</script>

<style>
.container {
  flex: 1;
  background-color: white;
  align-items: center;
  justify-content: center;
}
.text-color-primary {
  color: blue;
  font-size: 30;
}
</style>