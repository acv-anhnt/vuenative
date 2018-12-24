<template>
    <Text v-if="isShowingText">{{text}}</Text>
</template>

<script>
export default {
  props: {
    text: {
      Type: String
    }
  },
  data(){
    return {
      isShowingText: true,
    }
  },
  computed: {
    isShow(){
      return this.isShowingText 
    }
  },
  beforeMount() {
    _this = this
    setInterval(function(){
      _this.$set(_this, 'isShowingText', !_this.isShowingText)
    }, 1000)
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