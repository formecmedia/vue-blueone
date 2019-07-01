<template>
  <div id="home">
    <div class="logo">
      <img src="../assets/logo.png" alt="Blueone" />
    </div>
    <Carousel />
    <div class="c-s">
      <h2>Our website is coming soon!</h2>
    </div>

    <div class="footer">
      <h4>Address</h4>
      <p>S.K. Orchid, Near, Shahu Mill Road, Bagal Chowk</p>
      <p>Kolhapur, Maharashtra 416008</p>
      <p class="email">office@blueone.in</p>
    </div>
  </div>
</template>

<script>
// @ is an alias to /src
import Carousel from "@/components/Carousel";

export default {
  name: "home",
  components: {
    Carousel
  }
};
</script>
<style lang="scss" scoped>
#home {
  position: relative;
  width: 100%;

  .logo {
    img {
      max-width: 200px;
      margin:16px 0;
    }
  }

  .c-s {
    padding: 16px 60px;
    background: rgba(255, 255, 255, 0.781);
    position: absolute;
    top: 40%;
    left: 50%;
    transform: translateX(-50%);
    z-index: 10000;

    @include for-phone-only{
      padding: 16px;
      width: 80%;
      top:70%;
    }
    h2 {
      color: black;
      font-size: 30px;
      text-transform: uppercase;
      font-weight: bold;

      @include for-phone-only{
        font-size: 22px;
      }
    }
  }

  .footer{
    margin-bottom: 16px;
    margin-top: 16px;
    h4{
      text-transform: uppercase;
      position: relative;
      display: inline-block;
      margin-bottom: 8px;
    }

    h4::after{
      content: '';
      width: 100%;
      height: 2px;
      background: rgba(0, 0, 0, 0.404);
      position: absolute;
      bottom: -2px;
      left: 0;
    }

    .email{
      font-style: italic;
    }
  }
}
</style>

