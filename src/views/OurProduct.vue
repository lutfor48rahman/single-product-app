<template>
  <div class="ourProduct">
    <div class="container products">
      <p class="title">আমরা যে ধরনের পোলো টি শার্ট সেলস করে থাকিঃ</p>
      <div class="row">
        <div
          v-for="product in products"
          :key="product.id"
          class="col-12 col-lg-4"
        >
          <div class="singleProduct">
              <img :src="product.img" alt="" />
              <p class="name">beautiful color shart</p>
          </div>
        </div>
      </div>
      <div class="buttonDiv">
        <button class="showProduct">Show more</button>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "SingleProductAppOurProduct",

  data() {
    return {
      products: [
        { img: "https://i.ibb.co/PDfrBBF/image-3.png", id: 1 },
        { img: "https://i.ibb.co/dG9jG4Q/image-4.png", id: 2 },
        { img: "https://i.ibb.co/4fwq7ym/image-5.png", id: 3 },
        { img: "https://i.ibb.co/dG9jG4Q/image-4.png", id: 4 },
        { img: "https://i.ibb.co/4fwq7ym/image-5.png", id: 3 },
        { img: "https://i.ibb.co/PDfrBBF/image-3.png", id: 1 },
      ],
    };
  },

  mounted() {},

  methods: {},
};
</script>

<style>
.ourProduct {
  margin-top: 60px;
  background: #dea90b;
}
.ourProduct .products {
  padding-top: 100px;
}
.ourProduct .title {
  text-align: center;
  padding: 5px;
  font-family: "Poppins";
  font-style: normal;
  font-weight: 600;
  font-size: 26px;
  color: #000000;
  margin-bottom: 50px;
}
.singleProduct {
  position: relative;
}
.ourProduct img {
  height: 364px;
  width: 330px;
  background: white;
  margin-bottom: 40px;
  border-radius: 5px;
}

.singleProduct .name {
  height: 40px;
  width: 330px;
  background: #ffffff;
  box-shadow: 0px -7px 40px rgba(0, 0, 0, 0.2);
  border-radius: 25px 25px 4px 4px;
  position: absolute;
  left: 0;
  right: 0;
  bottom: 25px;
  display: flex;
  place-content: center;
  place-items: center;
}
.ourProduct .buttonDiv {
  display: flex;
  place-content: center;
}
.ourProduct .products .showProduct {
  margin-top: 50px;
  margin-bottom: 50px;
  width: 215px;
  height: 52px;
  border: none;
  border-radius: 5px;
  background: #ffffff;
  box-shadow: 0px 0px 40px rgba(0, 0, 0, 0.2);
}
@media screen and (max-width: 768px) {
  
}
</style>