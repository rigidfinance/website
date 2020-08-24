<template>
  <div id="roadmap">
    <BigTitle title="Our Roadmap"/>
    <SubTitle subtitle-first="Join our telegram channel to "
              subtitle-second=" learn more about our roadmap."/>
    <div class="container">
      <div class="row">
        <section class="timeline">
          <article>
            <div class="inner">
                <span class="date">
        <span class="day">14</span>
        <span class="month">Jul</span>
        <span class="year">2020</span>
      </span>
              <h2>Coming out of the idea and building the team</h2>
            </div>
          </article>
          <article>
            <div class="inner">
      <span class="date">
        <span class="day">31</span>
        <span class="month">Aug</span>
        <span class="year">2020</span>
      </span>
              <h2>Presale</h2>
            </div>
          </article>
          <article>
            <div class="inner">
      <span class="date">
        <span class="day">3</span>
        <span class="month">SEP</span>
        <span class="year">2020</span>
      </span>
              <h2>Sale</h2>
            </div>
          </article>
          <article>
            <div class="inner">
      <span class="date">
        <span class="day">1</span>
        <span class="month">Dec</span>
        <span class="year">2020</span>
      </span>
              <h2>First release in beta.</h2>
            </div>
          </article>
          <article>
            <div class="inner">
      <span class="date">
        <span class="day">1</span>
        <span class="month">Jan</span>
        <span class="year">2020</span>
      </span>
              <h2>Voting for selection of design and logo</h2>
            </div>
          </article>
          <article>
            <div class="inner">
      <span class="date">
        <span class="day">1</span>
        <span class="month">Mar</span>
        <span class="year">2020</span>
      </span>
              <h2>Release</h2>
            </div>
          </article>
        </section>
      </div>
    </div>
  </div>
</template>

<script>
import BigTitle from "@/components/BigTitle";
import SubTitle from "@/components/SubTitle";

export default {
  name: "Roadmap",
  components: {SubTitle, BigTitle}
}
</script>

<style scoped lang="scss">
#roadmap {
  background-color: #171055;

  section.timeline {
    width: 80%;
    margin: 20px auto;
    position: relative;

    &:before {
      content: '';
      display: block;
      position: absolute;
      left: 50%;
      top: 0;
      margin: 0 0 0 -1px;
      width: 2px;
      height: 100%;
      background: rgba(255, 255, 255, 0.2);
    }

    article {
      width: 100%;
      margin: 0 0 20px 0;
      position: relative;

      &:after {
        content: '';
        display: block;
        clear: both;
      }

      div.inner {
        width: 40%;
        float: left;
        margin: 5px 0 0 0;
        border-radius: 6px;

        span.date {
          display: block;
          width: 60px;
          height: 50px;
          padding: 5px 0;
          position: absolute;
          top: 0;
          left: 50%;
          margin: 0 0 0 -32px;
          border-radius: 100%;
          font-size: 12px;
          font-weight: 900;
          text-transform: uppercase;
          background: #2735b5;
          color: white;
          box-shadow: 0 0 0 7px #2735b5;

          span {
            display: block;
            text-align: center;

            &.day {
              font-size: 10px;
            }

            &.month {
              font-size: 18px;
            }

            &.year {
              font-size: 10px;
            }
          }
        }

        h2 {
          padding: 15px;
          margin: 0;
          color: #fff;
          font-size: 20px;
          text-transform: uppercase;
          letter-spacing: -1px;
          border-radius: 6px 6px 0 0;
          position: relative;

          &:after {
            content: '';
            position: absolute;
            top: 20px;
            right: -5px;
            width: 10px;
            height: 10px;
            -webkit-transform: rotate(-45deg);
          }
        }

        p {
          padding: 15px;
          margin: 0;
          font-size: 14px;
          background: #fff;
          color: #656565;
          border-radius: 0 0 6px 6px;
        }
      }

      &:nth-child(2n+2) div.inner {
        float: right;

        h2:after {
          left: -5px;
        }
      }

      div.inner h2 {
        background: #2735b5;

        &:after {
          background: #2735b5;
        }
      }


    }
  }

}
</style>
