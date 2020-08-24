<template>
  <div id="initial">
    <div class="container">
      <div class="row">
        <div class="col-sm-12 col-md-6">
          <div class="initial-content">
            <h1>Rigid Finance and DeFi can change the financial systems.</h1>
            <h3>Rigid Finance offers peer to peer exchange for Ethereum tokens at the lowest cost. It is easy to use and
              free. You won't have any trouble using Rigid Finance.</h3>


            <div id="countdown">
              <div><span class="days"></span>
                <div class="smalltext">Days</div>
              </div>
              <div><span class="hours"></span>
                <div class="smalltext">Hours</div>
              </div>
              <div><span class="minutes"></span>
                <div class="smalltext">Minutes</div>
              </div>
              <div><span class="seconds"></span>
                <div class="smalltext">Seconds</div>
              </div>
            </div>

            <button @click="smartContractTabbed" rel="nofollow" class="whitepaper-link">SMART CONTRACT</button>
          </div>
        </div>
        <div class="col-md-6">
          <div class="initial_vector"></div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "InitialView",
  data(){
    return{
      deadline: 'Aug 31 2020 17:00:00 UTC',
    }
  },
  mounted() {
    this.run_clock('countdown', this.deadline);
  },
  methods: {
    smartContractTabbed() {
      alert("Smart contract adress is coming..")
    },
    time_remaining(endtime){
      var t = Date.parse(endtime) - Date.parse(new Date());
      var seconds = Math.floor( (t/1000) % 60 );
      var minutes = Math.floor( (t/1000/60) % 60 );
      var hours = Math.floor( (t/(1000*60*60)) % 24 );
      var days = Math.floor( t/(1000*60*60*24) );
      return {'total':t, 'days':days, 'hours':hours, 'minutes':minutes, 'seconds':seconds};
    },
    run_clock(id,endtime){
      var clock = document.getElementById(id);

      // get spans where our clock numbers are held
      var days_span = clock.querySelector('.days');
      var hours_span = clock.querySelector('.hours');
      var minutes_span = clock.querySelector('.minutes');
      var seconds_span = clock.querySelector('.seconds');

      let self = this;

      function update_clock(){
        var t = self.time_remaining(endtime);

        // update the numbers in each part of the clock
        days_span.innerHTML = t.days;
        hours_span.innerHTML = ('0' + t.hours).slice(-2);
        minutes_span.innerHTML = ('0' + t.minutes).slice(-2);
        seconds_span.innerHTML = ('0' + t.seconds).slice(-2);

        if(t.total<=0){ clearInterval(timeinterval); }
      }
      update_clock();
      var timeinterval = setInterval(update_clock,1000);
    }
  }
}
</script>

<style scoped lang="scss">
#initial {
  padding-top: 80px;
  padding-bottom: 80px;
  background-color: #171055;
  height: calc(100vh - 92px);
  min-height: 100vh;
  min-width: 100vw;

  .initial-content {
    margin-top: 80px;
    margin-bottom: 160px;
    text-align: center;
    display: flex;
    align-items: center;
    justify-content: center;
    flex-direction: column;

    h1 {
      font-size: 40px;
      color: #ffffff;
      line-height: 45px;
      text-align: center;
      font-weight: 700;
      font-style: normal;

      span {
        font-size: 60px;
      }
    }

    h3 {
      font-size: 20px;
      color: #ffffff;
      line-height: 24px;
      text-align: center;
      font-weight: 400;
      font-style: normal;
      margin-bottom: 60px;
    }

    .whitepaper-link {
      color: #ffffff;
      padding: 12px 45px;
      border: none;
      border-radius: 5px;
      text-transform: uppercase;
      font-weight: bold;
      font-size: 13px;
      box-shadow: 0 0 5px 0 rgba(75, 171, 248, 1);
      background: #4babf8;
      background: linear-gradient(to left, #4babf8 0%, #2d6ff6 40%, #4babf8 100%);
      background-size: 200% 200%;
      transition: all 250ms ease-in;
      cursor: pointer;
      text-decoration: none;

      &:hover {
        border-color: rgba(255, 255, 255, 0.01);
        background-position: 100% !important;
      }

      &:focus {
        outline: 0;
      }
    }

  }

  .initial_vector {
    background-image: url("~assets/img/vector.png");
    background-position-y: center;
    height: 100%;
    width: 100%;
    background-size: contain;
    background-repeat: no-repeat;
    display: flex;
    align-items: center;
    justify-content: center;
    flex-direction: column;
  }

  #countdown {
    font-family: sans-serif;
    color: #fff;
    display: inline-block;
    font-weight: 100;
    text-align: center;
    font-size: 30px;

    & > div {
      padding: 25px;
      border-radius: 10px;
      background: #4babf8;
      background: linear-gradient(to left, #4babf8 0%, #2d6ff6 40%, #4babf8 100%);
      background-size: 200% 200%;
      display: inline-block;
      box-shadow: 0 0 5px 0 rgba(75, 171, 248, 1);
      margin-bottom: 10px;
    }

    div > span {
      padding: 15px;
      border-radius: 3px;
      background: #171055;
      display: inline-block;
      color: white;

    }

    .smalltext {
      padding-top: 5px;
      font-size: 16px;
    }


  }
}

</style>
