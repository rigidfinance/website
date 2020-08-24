<template>
  <div id="content_one">
    <div class="container">
      <div class="row">
        <div class="col-sm-6">
          <div class="content-image"></div>
        </div>
        <div class="col-sm-6">
          <h3 class="content-title">
            No need for extra information
          </h3>
          <div class="content-desc">
            You don't need to register or provide us with information to exchange tokens. You will not be dealing with anyone in transactions made from peer to peer. You can exchange tokens belonging to another with your own tokens as much as you want.
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "ContentTwo"
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
