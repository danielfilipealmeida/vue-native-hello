<template>
  <view class="container">
    <text class="text-color-primary">{{message}}</text>
    <button :on-press="onButtonPress" title="Go to Product Detail"/>
  </view>
</template>

<script>
export default {
  props: {
    navigation: {
      type: Object
    }
  },
  methods: {
    onButtonPress: function() {
      this.navigation.navigate("ProductDetail");
    }
  },
  data: function() {
    return {
      message: "Catalogue screen"
    };
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
  color: red;
  font-size: 30;
}
</style>