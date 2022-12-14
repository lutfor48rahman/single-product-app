<template>
  <div class="ourGallery">
    <dir class="container">
      <p class="title">ফটো গ্যালারী</p>
      <div class="row">
        <div
          v-for="product in products"
          :key="product.id"
          class="col-12 col-lg-4"
        >
          <div class="gallery">
            <img :src="product.img" alt="" />
          </div>
        </div>
      </div>
      <div class="galleryButton">
        <button>More images</button>
      </div>
    </dir>
  </div>
</template>

<script>
export default {
  name: "SingleProductAppPhotoGallery",

  data() {
    return {
      products: [
        { img: "https://i.ibb.co/2yZPJgx/Rectangle-39.png", id: 1 },
        { img: "https://i.ibb.co/8cS8KBZ/Rectangle-35-1.png", id: 2 },
        { img: "https://i.ibb.co/BjbF4fR/Rectangle-34.png", id: 3 },
        { img: "https://i.ibb.co/1XtZFsj/Rectangle-37-1.png", id: 4 },
        { img: "https://i.ibb.co/988XmQF/Rectangle-38.png", id: 5 },
        { img: "https://i.ibb.co/2yZPJgx/Rectangle-39.png", id: 6 },
      ],
    };
  },

  mounted() {},

  methods: {},
};
</script>

<style>
.ourGallery {
    
}
.ourGallery .title {
  font-family: "Poppins";
  font-style: normal;
  font-weight: 600;
  font-size: 26px;
  color: #000000;
  text-align: center;
  padding-top: 80px;
  padding-bottom: 30px;
}
.ourGallery .gallery {
    text-align: center;
}
.ourGallery .gallery img {
  height: 354px;
  margin-bottom: 25px;
  background: white;
  margin-bottom: 50px;
  border-radius: 5px;
}
.ourGallery .galleryButton{
    text-align: center;
    padding-bottom: 30px;
}
.ourGallery .galleryButton button{
    width: 200px;
height: 52px;
background: #DEA90B;
box-shadow: 0px 0px 40px #DEA90B;
border: none;
border-radius: 4px;
}
</style>