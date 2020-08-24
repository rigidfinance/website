<template>
  <div id="faq">
    <div class="container">
      <BigTitle title="FAQ"/>
      <SubTitle subtitle-first="If your questions are not listed in the FAQ,"
                subtitle-second="you can ask them in our telegram channel."/>
      <div class="row">
        <div class="col-md-6">
          <div class="tabs">
            <div class="tab">
              <input type="checkbox" id="chck1">
              <label class="tab-label" for="chck1">What is Rigid Finance?</label>
              <div class="tab-content">
                Rigid finance is a project that set out to make your token swap transaction from mobile or other
                platforms faster. Our goal is to establish a completely decentralized exchange.
              </div>
            </div>
            <div class="tab">
              <input type="checkbox" id="chck2">
              <label class="tab-label" for="chck2">Why is your team anonymous?</label>
              <div class="tab-content">
                While creating decentralized finance, we hid ourselves in the belief that individuals would increase
                centralization. Our main goal is to create a revolutionary swap environment that is completely
                independent of the person. So don't worry, everything is safe with smart contracts
              </div>
            </div>
            <div class="tab">
              <input type="checkbox" id="chck3">
              <label class="tab-label" for="chck3">Who does your team consist of?</label>
              <div class="tab-content">
                In addition to 3 community managers who will support you in Telegram, 5 full stack developers will
                develop Rigid. These people who are completely experts in their field and they will work hard to make
                unique.
              </div>
            </div>
            <div class="tab">
              <input type="checkbox" id="chck4">
              <label class="tab-label" for="chck4">When will the whitepaper be released?</label>
              <div class="tab-content">
                We want to publish the whitepaper right after sale and we are doing the final checks now. Do not
                forget to join our telegram channel to get more information!
              </div>
            </div>
          </div>
        </div>
        <div class="col-md-6">
          <div class="tabs">
            <div class="tab">
              <input type="checkbox" id="chck5">
              <label class="tab-label" for="chck5">How can I trust you?</label>
              <div class="tab-content">
                You don't have to trust anyone. In Rigid Finance, all transactions are secured with smart contract and published with open source code. We cannot change the token distribution we specified anyway!
              </div>
            </div>
            <div class="tab">
              <input type="checkbox" id="chck6">
              <label class="tab-label" for="chck6">Will there be any tokens other than locked tokens?</label>
              <div class="tab-content">
                No, there won't be any! We will not create more and you will be able to check this from contracts already published as open source code.
              </div>
            </div>
            <div class="tab">
              <input type="checkbox" id="chck7">
              <label class="tab-label" for="chck7">When will you be on Uniswap?</label>
              <div class="tab-content">
                We will enter Uniswap right after the token sale is over.
              </div>
            </div>
            <div class="tab">
              <input type="checkbox" id="chck8">
              <label class="tab-label" for="chck8">Will there be on other exchanges?</label>
              <div class="tab-content">
                Of course it will, but it's too early to think about it right now. We will make the Exchange announcements through the telegram channel. Our goal is to enter one of the top 10 exchanges in the first 6 months.
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

export default {
  name: "FAQ",
  components: {SubTitle, BigTitle}
}
</script>

<style scoped lang="scss">

#faq {
  background-color: #171055;
}

$midnight: #2735b5;
$clouds: #ecf0f1;
// General
body {
  color: $midnight;
  background: $clouds;
  padding: 0 1em 1em;
}

h1 {
  margin: 0;
  line-height: 2;
  text-align: center;
}


input {
  position: absolute;
  opacity: 0;
  z-index: -1;
}


/* Accordion styles */
.tabs {
  border-radius: 8px;
  overflow: hidden;
  box-shadow: 0 4px 4px -2px rgba(0, 0, 0, 0.5);
}

.tab {
  width: 100%;
  color: white;
  overflow: hidden;

  &-label {
    display: flex;
    justify-content: space-between;
    padding: 1em;
    background: $midnight;
    font-weight: bold;
    cursor: pointer;
    /* Icon */
    &:hover {
      background: darken($midnight, 10%);
    }

    &::after {
      content: "\276F";
      width: 1em;
      height: 1em;
      text-align: center;
      transition: all .35s;
    }
  }

  &-content {
    max-height: 0;
    padding: 0 1em;
    color: $midnight;
    background: white;
    transition: all .35s;
  }

  &-close {
    display: flex;
    justify-content: flex-end;
    padding: 1em;
    font-size: 0.75em;
    background: $midnight;
    cursor: pointer;

    &:hover {
      background: darken($midnight, 10%);
    }
  }
}

// :checked
input:checked {
  + .tab-label {
    background: darken($midnight, 10%);

    &::after {
      transform: rotate(90deg);
    }
  }

  ~ .tab-content {
    max-height: 100vh;
    padding: 1em;
  }
}

</style>
