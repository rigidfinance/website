<template>
  <div id="content_one">
    <div class="container">
      <div class="row">
        <div class="col-sm-6">
          <h3 class="content-title">
            No need for extra security
          </h3>
          <div class="content-desc">
            We will already have taken all safety measures for you with smart contracts. You don't need to take an effort and take a security measure for more. You just need to keep your wallet safe. You don't need to trust us either! Our smart contracts will provide all the security you need!
          </div>
        </div>
        <div class="col-sm-6">
          <div class="content-image"></div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "ContentThree"
}
</script>

<style scoped lang="scss">
#content_one {
  padding: 100px 0;
  background-color: #171055;
  .content-title{
    text-transform: uppercase;
    font-weight: 800;
    font-size: 30px;
    line-height: 35px;
    color: white;
  }
  .content-desc{
    opacity: 0.7;
    color: white;
  }
  .content-image{
    background-image: url("~assets/img/content-one.png");
    height: 100%;
    background-size: contain;
    background-repeat: no-repeat;
    background-position: center;
  }
}
</style>
