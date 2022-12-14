<template>
  <div class="aboutProduct">
    <div class="container">
      <div class="row">
        <div class="col-12 col-lg-6 contents">
          <div class="">
            <p class="title">Lorem ipsum dolor sit amet consectetur</p>
            <p class="text">
              Lorem ipsum dolor sit, amet consectetur adipisicing elit. Neque
              obcaecati hic error illum quam quo modi quas similique, soluta
              alias.obcaecati hic error illum quam quo modi quas similique,
              soluta alias.
            </p>
            <button class="button1">Let's Chat Now!</button>
            <button class="button2"><ChatIcon /> Order now</button>
          </div>
        </div>
        <div class="col-12 col-lg-6">
          <div class="aboutBg">
            <img :src="img" :alt="name" />
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>

export default {
  name: "SingleProductAppAboutProduct",
  components: {  },
  data() {
    return {
      img: "https://i.ibb.co/zF6HfL5/image-2-1.png",
      name: "first picture",
    };
  },

  mounted() {},

  methods: {},
};
</script>

<style>
.aboutProduct {
  margin-top: 80px;
}
.aboutProduct .contents {
  display: flex;
  place-content: center;
  place-items: center;
}
.aboutProduct .title {
  width: 450px;
  font-family: "Poppins";
  font-style: normal;
  font-weight: 500;
  font-size: 46px;
  line-height: 69px;
  letter-spacing: 0.095em;

  color: #000000;
}
.aboutProduct .text {
  width: 410px;

  font-family: "Poppins";
  font-style: normal;
  font-weight: 500;
  font-size: 24px;
  line-height: 36px;

  color: #000000;
}
.aboutBg {
  width: 100%;
  height: 200px;
  display: flex;
  place-content: center;
  place-items: center;
}
.aboutProduct .aboutBg {
  background-image: url("https://i.ibb.co/0ZjMt01/Vector-1.png");
  height: 550px;
  width: 100%;
  background-position: center;
  background-size: auto;
  background-repeat: no-repeat;
}
.aboutBg img {
  margin-top: -30px;
  height: 450px;
  width: 100%;
}
.aboutProduct .button1 {
  width: 166px;
  height: 52px;
  border: none;
  background: #0075e0;
  border-radius: 4px;
}
.aboutProduct .button2 {
  width: 166px;
  height: 52px;
  margin-left: 20px;
  background: #dea90b;
  border: none;
  border-radius: 4px;
}
</style>