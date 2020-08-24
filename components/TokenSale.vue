<template>
  <div id="tokensale">
    <div class="container">
      <BigTitle title="TOKEN SALE DETAILS"/>
      <SubTitle subtitle-first="Our first goal in token distribution is to make"
                subtitle-second="a fair share for everyone."/>

      <div class="row">
        <div class="col-md-12">
          <div id="distribution">
            <Distribution :height="200" />
          </div>
        </div>
      </div>
      <div class="row">
        <div class="col-md-12">
          <div class="token-details-one">
            <div class="row">
              <div class="col-sm-4">
                <h2 class="total">Total contribution:</h2>
                <h2 class="amount">1,200 ETH</h2>
              </div>
              <div class="col-sm-2" v-for="coin in this.coinData">
                <div>
                  <p class="price">
                    <span class="name">{{ coin.name }}: </span>
                    <span class="value">${{Number(coin.priceUsd).toFixed(1)}}</span>
                  </p>
                </div>
              </div>

            </div>
          </div>
        </div>
      </div>
      <div class="row">
        <div class="col-md-12">
          <div class="token-details-two">
            <div class="row">
              <div class="col-sm-6 special-border">
                <p>
                  <font-awesome-icon color="white" :icon="['fas', 'hand-point-right']"/>
                  <span class="name">Token Name</span><span class="value pull-right">RIGID TOKEN</span>
                </p>
                <p>
                  <font-awesome-icon color="white" :icon="['fas', 'hand-point-right']"/>
                  <span class="name">Token Symbol</span><span class="value pull-right">RGD</span>
                </p>
                <p>
                  <font-awesome-icon color="white" :icon="['fas', 'hand-point-right']"/>
                  <span class="name">Total Supply</span><span class="value pull-right">8,000,000</span>
                </p>
                <p>
                  <font-awesome-icon color="white" :icon="['fas', 'hand-point-right']"/>
                  <span class="name">Circulating Supply</span><span class="value pull-right">4,800,000</span>
                </p>
                <p>
                  <font-awesome-icon color="white" :icon="['fas', 'hand-point-right']"/>
                  <span class="name">Token Price</span><span class="value pull-right">0.00027 ETH</span>
                </p>
              </div>
              <div class="col-sm-6">
                <p>
                  <font-awesome-icon color="white" :icon="['fas', 'hand-point-right']"/>
                  <span class="name">Per 1 Ethereum (PRE-SALE)</span><span class="value pull-right">4,600 RGD</span>
                </p>
                <p>
                  <font-awesome-icon color="white" :icon="['fas', 'hand-point-right']"/>
                  <span class="name">Per 1 Ethereum (SALE)</span><span class="value pull-right">3,700 RGD</span>
                </p>
                <p>
                  <font-awesome-icon color="white" :icon="['fas', 'hand-point-right']"/>
                  <span class="name">Hardcap</span><span class="value pull-right">1,200 ETH</span>
                </p>
                <p>
                  <font-awesome-icon color="white" :icon="['fas', 'hand-point-right']"/>
                  <span class="name">Presale Hardcap</span><span class="value pull-right">400 ETH</span>
                </p>
                <p>
                  <font-awesome-icon color="white" :icon="['fas', 'hand-point-right']"/>
                  <span class="name">Sale Hardcap</span><span class="value pull-right">800 ETH</span>
                </p>
              </div>
            </div>
          </div>
        </div>
      </div>

    </div>
  </div>
</template>

<script>
import BigTitle from "@/components/BigTitle";
import SubTitle from "@/components/SubTitle";
import Distribution from "@/components/Distribution";

export default {
  name: "TokenSale",
  components: {SubTitle, BigTitle, Distribution},
  data(){
   return{
     coinData: null
   }
  },
  async mounted() {
    await this.fetchData();
  },
  methods: {
    async fetchData() {
      await this.$axios.$get(`https://api.coincap.io/v2/assets?limit=4`)
        .then(res => {
          this.coinData = res['data'];
          return {coinData: res['data']}
        })
    },
  }
}
</script>

<style scoped lang="scss">
#tokensale {
  background-color: #171055;

  .token-details-one {
    background-color: #2735b5 !important;
    margin-bottom: 10px;
    padding: 50px 35px;
    border-radius: 5px;

    .total {
      font-size: 20px;
      color: #ffffff;
      line-height: 25px;
      text-align: left;
      font-weight: 700;
      font-style: normal;
      margin: 10px;
    }

    .amount {
      font-size: 30px;
      color: #ffffff;
      line-height: 35px;
      text-align: left;
      font-weight: 700;
      font-style: normal;
      text-indent: 20px;
      margin: 0px;
    }

    span.name {
      font-weight: bold;
      color: white;
      font-size: 15px;
    }

    span.value {
      opacity: .7;
      color: white;
    }
  }

  .special-border {
    border-right: 1px solid #3d4abd;
  }

  .token-details-two {
    background-color: #2735b5 !important;
    margin-bottom: 10px;
    padding: 50px 35px;
    border-radius: 5px;

    p {
      margin: 0 0 20px 0;
      padding: 5px;

      .svg-inline--fa {
        float: left;
      }

      .name {
        float: left;
        color: white;
        font-weight: bold;
        padding-left: 5px;
        display: inline-block;
      }

      .value {
        float: right;
        color: white;
        opacity: 0.7;
      }
    }

  }

  #distribution{
    padding-bottom: 60px;
    padding-top: 0px;
  }
}
</style>
