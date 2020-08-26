<template>
  <div class="home">
    <h1>Home</h1>
    <CustomText>Merhaba Dünya</CustomText>
    <CustomText tag="p">Merhaba Dünya</CustomText>
    <CustomText tag="b" size="xsmall">Merhaba Dünya</CustomText>
  </div>
</template>

<script>
import CustomText from '@/components/CustomText'


export default {
  name: 'Home',
  component: {
    CustomText
  }
}
</script>

<style>
h1 {
  color: red;

  @media (--t) {
    color: blue;
  }
}
</style>
