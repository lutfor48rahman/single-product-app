<template>
  <div class="container">
    <div class="chooseModal">
      <div class="mainModal">
        <div class="row">
          <div class="col-12 col-lg-6">
            <div class="modalImage">
              <img :src="img" alt="" />
            </div>
          </div>
          <div class="col-12 col-lg-6">
            <div class="modalContent">
              <p class="modalHeading">Polo Shirt 3D Design</p>
              <p class="modalPrice">&#2547; {{ price }}<span></span></p>
            </div>
            <form @submit.prevent="handleSubmit">
              <div class="modalForm">
                <div class="modalSelect">
                  <label class="size" for="">Size</label>
                  <select name="" id="" v-model="sizeSelect">
                    <option
                      v-for="size in sizes"
                      :key="size.id"
                      :value="size.name"
                    >
                      {{ size.name }}
                    </option>
                  </select>
                </div>
                <div class="modalSelect">
                  <label for="">Color</label>
                  <select name="" id="" v-model="colorSelect">
                    <option
                      v-for="color in colors"
                      :key="color.id"
                      :value="color.name"
                    >
                      {{ color.name }}
                    </option>
                  </select>
                </div>
                <hr />
              </div>
              <div class="modalButton">
                <button @click="dataPass">Add To Cart</button>
              </div>
            </form>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "SingleProductAppChooseModal",

  data() {
    return {
      img: "https://i.ibb.co/PDfrBBF/image-3.png",
      sizes: [
        { name: "Choose an option", id: 1 },
        { name: "M", id: 2 },
        { name: "L", id: 3 },
        { name: "XL", id: 4 },
      ],
      colors: [
        { name: "Choose an option", id: 1 },
        { name: "Red", id: 2 },
        { name: "Blue", id: 3 },
        { name: "Black", id: 4 },
      ],
      sizeSelect: "Choose an option",
      colorSelect: "Choose an option",
    };
  },
  props: ["price"],

  mounted() {},

  methods: {
    handleSubmit() {
      // console.log(this.sizeSelect,this.colorSelect);
    },
    dataPass() {
      this.$emit("dataGet", this.sizeSelect, this.colorSelect);
    },
  },
};
</script>

<style>
.chooseModal {
  position: fixed;
  top: 10%;
  left: 10%;
  background: white;
  width: 80%;
  min-height: 80%;
  box-shadow: rgba(50, 50, 93, 0.25) 0px 6px 12px -2px,
    rgba(0, 0, 0, 0.3) 0px 3px 7px -3px;
  border-radius: 10px;
}
.mainModal {
  width: 100%;
  margin: 80px auto;
  border-radius: 10px;
}
.mainModal .modalImage {
  display: flex;
  justify-content: center;
  align-items: center;
}
.mainModal .modalImage img {
  height: 300px;
  width: 50%;
}
.modalContent,
.chooseModal form {
  margin-left: 20px;
}
.modalContent .modalHeading {
  font-family: "Inter";
  font-style: normal;
  font-weight: 500;
  font-size: 35px;
  color: #000000;
}
.modalContent .modalPrice {
  color: green;
  font-size: 20px;
}
.modalForm .modalSelect {
  display: flex;
}
.modalForm .modalSelect .size {
  margin-right: 10px;
}
.modalForm .modalSelect label {
  font-size: 18px;
  font-family: "Inter";
  font-style: normal;
  color: rgb(105, 104, 104);
}
.modalForm .modalSelect select {
  margin-bottom: 20px;
  height: 35px;
  width: 50%;
  margin-left: 30px;
  padding-left: 10px;
  border: 1px solid rgb(187, 186, 186);
  border-radius: 5px;
  appearance: none;
  outline: none;
  cursor: pointer;
}
.modalButton {
  margin-top: 30px;
}
.modalButton button {
  height: 40px;
  width: 170px;
  border: none;
  border-radius: 5px;
  background: rgb(247, 99, 45);
  color: white;
}

@media screen and (max-width: 768px) {
  .chooseModal {
    width: 80%;
    height: 30%;
    overflow: scroll;
  }
  .chooseModal {
    overflow-y: scroll;
  }
}
</style>