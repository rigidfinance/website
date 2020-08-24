<template>
  <div class="subtitle">{{subtitleFirst}} <br> {{subtitleSecond}}</div>
</template>

<script>
export default {
  name: "SubTitle",
  props: {
    subtitleFirst: {
      type: String,
      required: true
    },
    subtitleSecond: {
      type: String,
      required: true
    },
  }
}
</script>

<style scoped lang="scss">
.subtitle{
  color: #ffffff;
  opacity: 0.7;
  font-size: 16px;
  font-weight: 500;
  text-align: center;
  width: 70%;
  margin: 0 auto;
  margin-top: 5px;
  padding-bottom: 100px;
}
</style>
