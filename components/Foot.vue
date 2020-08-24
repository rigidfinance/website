<template>
  <div id="foot">
    <div class="container">
      <div class="row">
        <div class="col-md-12">
          <div class="content-center">
            <a href="https://twitter.com/rigidfinance" rel="nofollow" target="_blank">
              <font-awesome-icon color="white" class="fa-2x"  :icon="['fab', 'twitter']"/>
            </a>
            <a href="https://t.me/rigidfinance" rel="nofollow" target="_blank">
              <font-awesome-icon color="white" class="fa-2x"  :icon="['fab', 'telegram']"/>
            </a>
            <a href="https://github.com/rigidfinance" rel="nofollow" target="_blank">
              <font-awesome-icon color="white" class="fa-2x"  :icon="['fab', 'github']"/>
            </a>
            <button @click="redditAlert">
              <font-awesome-icon color="white" class="fa-2x"  :icon="['fab', 'reddit']"/>
            </button>
            <a href="https://medium.com/@rigidfinance" rel="nofollow" target="_blank">
              <font-awesome-icon color="white" class="fa-2x" :icon="['fab', 'medium']"/>
            </a>

          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "Foot",
  methods: {
    redditAlert(){
      alert("Reddit is coming..")
    }
  }
}
</script>

<style scoped lang="scss">
#foot {
  background-color: #2735b5 !important;
  position: relative;
  height: 70px;

  .content-center{
    display: flex;
    align-items: center;
    justify-content: center;
    text-align: center;
    color: white;
    a, button{
      line-height: 80px;
      display: block;
      margin-right: 10px;
    }
    button{
      appearance: none;
      background: none;
      border: none;
      cursor: pointer;
      &:focus{
        outline: 0;
      }
    }
  }



}
</style>
