<template>
  <view>
    <blink-text text='I love to blink'></blink-text>
    <blink-text text='Yes blinking is so great'></blink-text>
    <blink-text text='Why did they ever take this out of HTML'></blink-text>
    <blink-text text='Look at me look at me look at me'></blink-text>
  </view>
</template>

<script>
import BlinkText from "./components/blinkText";
export default {
  components: {BlinkText}
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