<template>
  <div class="ourBenefit">
    <div class="container">
      <p class="title">কেন আমাদের থেকে পোলো শার্ট নিবেন?</p>
      <div class="firstProductDiv">
        <div v-for="benefit in benefits" :key="benefit.name" class="whyProduct">
          <p class="singleBenefit"><span>&#x2713;</span> {{ benefit.name }}</p>
        </div>
      </div>
      <div class="secondProductDiv">
        <p class="name">আমাদের পোলো শার্ট এর সুবিধা</p>
        <div v-for="benefit in benefits" :key="benefit.name" class="secondWhyProduct">
          <p class="secondBenefit"><span>&#x2713;</span> {{ benefit.name }}</p>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "SingleProductAppBenefitOurProduct",

  data() {
    return {
      benefits: [
        { name: "Lorem ipsum dolor, sit amet consectetur", id: 1 },
        { name: "Lorem ipsum dolor, sit amet consectetur", id: 2 },
        { name: "Lorem ipsum dolor, sit amet consectetur", id: 3 },
        { name: "Lorem ipsum dolor, sit amet consectetur", id: 4 },
        { name: "Lorem ipsum dolor, sit amet consectetur", id: 5 },
      ],
    };
  },

  mounted() {},

  methods: {},
};
</script>

<style>
.ourBenefit {
  margin-top: 50px;
  background: #dea90b;
}
.ourBenefit .title {
  padding-top: 60px;
  padding-bottom: 30px;
  text-align: center;
  font-family: "Poppins";
  font-style: normal;
  font-weight: 600;
  font-size: 26px;
  color: #000000;
}
.firstProductDiv {
  padding-bottom: 50px;
}
.ourBenefit .whyProduct {
  text-align: center;
}
.ourBenefit .singleBenefit {
  width: 70%;
  height: 52px;
  margin: auto;
  margin-bottom: 20px;
  background: #ffffff;
  box-shadow: 0px 0px 12px rgba(0, 0, 0, 0.15);
  border-radius: 4px;
  display: flex;
  justify-content: center;
  align-items: center;
}
.ourBenefit .whyProduct .singleBenefit span {
  height: 25px;
  width: 25px;
  margin-right: 15px;
  color: white;
  background: #0075e0;
  font-size: 18px;
  border-radius: 50%;
}
.secondProductDiv {
    padding-bottom: 50px;
}
.secondProductDiv .name {
    text-align: center;
  font-family: "Poppins";
  font-style: normal;
  font-weight: 600;
  font-size: 26px;
  line-height: 200%;
  color: #000000;
  margin-bottom: 20px;
}
.secondProductDiv .secondWhyProduct{
    text-align: start;
}
.ourBenefit .secondBenefit {
  width: 70%;
  height: 52px;
  margin: auto;
  margin-bottom: 20px;
  background: #ffffff;
  box-shadow: 0px 0px 12px rgba(0, 0, 0, 0.15);
  border-radius: 4px;
  display: flex;
  justify-content: start;
  align-items: center;
  padding-left: 80px;
}
.ourBenefit .secondWhyProduct .secondBenefit span{
  height: 25px;
  width: 25px;
  margin-right: 15px;
  padding-left: 4px;
  padding-bottom: 4px;
  color: white;
  background: #0075e0;
  font-size: 18px;
  border-radius: 50%;

}
</style>