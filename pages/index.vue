<template>
  <div class="main">
    <Navigation/>
    <InitialView/>
    <TokenSale/>
    <div id="about">
      <ContentOne/>
      <ContentTwo/>
      <ContentThree/>
    </div>
    <Roadmap/>
    <FAQ/>
    <Newsletter/>
    <div id="telegram">
      <a href="https://t.me/rigidfinance" target="_blank" rel="nofollow">
        <font-awesome-icon color="#0088cc" class="fa-3x" :icon="['fab', 'telegram']"/>
      </a>
    </div>

  </div>
</template>

<script>
import Roadmap from "~/components/Roadmap";
import Navigation from "~/components/Navigation";
import InitialView from "~/components/InitialView";
import TokenSale from "@/components/TokenSale";
import Foot from "@/components/Foot";
import Newsletter from "@/components/Newsletter";
import FAQ from "@/components/FAQ";
import ContentOne from "@/components/ContentOne";
import ContentTwo from "@/components/ContentTwo";
import ContentThree from "@/components/ContentThree";

export default {
  components: {
    ContentThree,
    ContentTwo,
    ContentOne,
    FAQ,
    Newsletter,
    Foot,
    TokenSale,
    InitialView,
    Navigation,
    Roadmap
  },
  head() {
    return {
      title: "Rigid Finance"
    }
  }
}
</script>

<style lang="scss">
.main {
  #telegram {
    position: fixed;
    bottom: 20px;
    right: 20px;
    background: white;
    border-radius: 50%;
  }
}
</style>
