<template>
  <div class="feedback">
    <div class="container">
      <p class="title">আমাদের হ্যাপি কাস্টমারদের ফিডবেক দেখুন</p>
      <div class="row g-4">
        <div v-for="review in reviews" :key="review.id" class="col-12 col-lg-4">
          <div class="singleReview">
            <img :src="review.img" alt="" />
          </div>
        </div>
      </div>
      <div class="feedbackButton">
        <button>More Reviews</button>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "SingleProductAppFeedback",

  data() {
    return {
      reviews: [
        { img: "https://i.ibb.co/vJgptkv/Rectangle-41.png", id: 1 },
        { img: "https://i.ibb.co/RbLDvVP/Rectangle-42.png", id: 3 },
        { img: "https://i.ibb.co/fkrwbbg/Rectangle-43.png", id: 3 },
        { img: "https://i.ibb.co/0GB9mhw/Rectangle-44.png", id: 4 },
        { img: "https://i.ibb.co/vJgptkv/Rectangle-41.png", id: 1 },
      ],
    };
  },

  mounted() {},

  methods: {},
};
</script>

<style >
.feedback {
  background: #f5f5f5;
}
.feedback .title {
  font-family: "Poppins";
  font-style: normal;
  font-weight: 600;
  font-size: 26px;
  line-height: 200%;
  color: #000000;
  padding-top: 80px;
  margin-bottom: 50px;
  text-align: center;
}
.feedback .singleReview {
  text-align: center;
}
.feedback .singleReview img {
  height: 600px;
  width: 100%;
}
.feedback .feedbackButton {
  text-align: center;
  padding-bottom: 50px;
}
.feedback .feedbackButton button {
  width: 200px;
  height: 52px;
  background: #dea90b;
  box-shadow: 0px 0px 40px #dea90b;
  border-radius: 4px;
  border: none;
  margin-top: 50px;
}
</style>