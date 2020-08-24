<template>
<div id="social">

  <Foot />
</div>
</template>

<script>
import Foot from "@/components/Foot";
export default {
  name: "Newsletter",
  components: {Foot}
}
</script>

<style scoped lang="scss">
#social{
  min-width: 100vw;
  padding-top: 200px;
  display: flex;
  justify-content: space-between;
  flex-direction: column;
  #newsletter {
    padding-top: 200px;
    padding-bottom: 120px;
    background-color: #171055;

    h2 {
      font-size: 48px;
      color: #ffffff;
      line-height: 62px;
      text-align: center;
      font-family: 'Montserrat', sans-serif;
      font-weight: 700;
      display: block;
      font-style: normal;
    }

    p {
      font-size: 20px;
      color: rgba(255, 255, 255, 0.7);
      line-height: 30px;
      text-align: center;
      font-family: Montserrat;
      font-weight: 400;
      font-style: normal;
    }

    .newsletter{
      margin-bottom: 50px;
      .sign-up-input{

        background-position: 0%;
        background-size: 200% 200%;
        border-radius: 4px;
        display: -ms-flexbox;
        display: flex;
        -ms-flex-positive: 2;
        flex-grow: 2;
        transition: all .2s ease-in-out;
        height: 55px;
        margin-right: 10px;
        width: 65%;
        float: left;
        input{
          background: rgba(39, 53, 181, 0.9) !important;
          border-radius: 3px;
          height: 55px;
          font-size: 15px;
          border: 0 none;
          float: left;
          padding: 15px 25px;
          width: 100%;
          font-weight: 500;
          margin-right: 20px;
          color: white;
          &::placeholder{
            color: white;
            opacity: 0.7;
          }
        }
      }
      button{
        background-color: #252525;
        border: 0 none;
        float: left;
        font-style: normal;
        width: 30%;
        height: 55px;
        text-transform: uppercase;
        font-size: 15px;
        transition: all 300ms ease;
        background-image: linear-gradient(to left, #4babf8 0%, #2d6ff6 60%, #4babf8 100%);
        background-position: 0%;
        background-size: 200% 200%;
        border-radius: 4px;
        color: #fff;
        line-height: 1;
        min-width: 150px;
        padding: 10px 40px;
        margin-bottom: 10px;
        font-weight: bold;
        cursor: pointer;
        &:hover{
          border-color: rgba(255, 255, 255, 0.01);
          background-position: 100% !important;
        }
      }
    }
  }
}

</style>
