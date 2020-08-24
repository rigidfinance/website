<template>
  <h1 v-text="title"/>
</template>

<script>
export default {
  name: "BigTitle",

  props: {
    title: {
      type: String,
      required: true
    }
  }
}
</script>

<style scoped lang="scss">
h1 {
  background-color: #171055;
  text-align: center;
  text-transform: uppercase;
  font-weight: 800;
  font-size: 30px;
  line-height: 35px;
  margin: 0 !important;
  padding-bottom: 20px;
  padding-top: 50px;
  color: #ffffff;
}
</style>
