<template>
  <div class="customer">
    <div class="container">
      <div class="row">
        <div class="col-12 col-lg-7">
          <div class="heading">
            <p class="name">Customer information</p>
            <p class="account">
              Already have an account <a href="#">Log in</a>
            </p>
          </div>
          <div class="emailField">
            <label>Email Address *</label>
            <input type="text" placeholder="Email Address *" />
          </div>
          <div class="shipping">
            <p class="title">Billing & Shipping Details</p>
            <form>
              <div class="field">
                <label>Full name</label>
                <input type="text" />
              </div>
              <div class="field">
                <label>Phone</label>
                <input type="text" />
              </div>
            </form>
            <div class="countries">
              <div class="head">
                <p class="country">Country</p>
                <p class="name">Bangladesh</p>
              </div>
              <div class="detailsField">
                <div class="row">
                  <div class="col-12 col-lg-6 field">
                    <label>Street Address</label>
                    <input type="text" placeholder="House name & street name" />
                  </div>
                  <div class="col-12 col-lg-6 field">
                    <label>Apartment,suite,unit etc. (optional)</label>
                    <input type="text" placeholder="Apartment,suite & unit " />
                  </div>
                </div>
                <div class="row">
                  <div class="col-12 col-lg-4 field">
                    <label>Town/City</label>
                    <input type="text" />
                  </div>
                  <div class="col-12 col-lg-4 field">
                    <label>District</label>
                    <select
                      @click="nameHandle(role)"
                      v-model="role"
                      name=""
                      id=""
                    >
                      <option
                        v-for="district in districts"
                        :key="district.id"
                        :value="district.name"
                      >
                        {{ district.name }}
                      </option>
                    </select>
                  </div>
                  <div class="col-12 col-lg-4 field">
                    <label>Postcode/ZIP (optional)</label>
                    <input type="text" />
                  </div>
                </div>
              </div>
              <div></div>
            </div>
          </div>
        </div>
        <div class="col-12 col-lg-5">
          <div class="order">
            <p class="name">Your Product</p>
            <div class="mainBox">
              <div class="orderBox">
                <div class="productQuantity">
                  <div class="product">Product</div>
                  <div class="quantity">Quantity</div>
                </div>
                <div class="price">Price</div>
              </div>
              <hr />
              <div class="poloName">
                <p>Polo Shirt 3D Design (#24)</p>
              </div>
              <div class="select">
                <p class="checkBox"><input type="checkbox" checked /></p>
                <p>Size:{{size}}, Color: {{color}}</p>
                <div class="addQuantity">
                  <button @click="decreaseQuan" class="minus">
                    <span> &#8722;</span>
                  </button>
                  <p><input type="text" v-model="quantity" /></p>
                  <button @click="increaseQuan" class="plus">
                    <span> &#43;</span>
                  </button>
                </div>
                <div class="amount">
                  <p><span> &#2547;</span></p>
                  <p>{{ totalAmount }}</p>
                </div>
              </div>
              <div class="variation">
                <p class="modalShow" @click="getData">Choose a Variation</p>
              </div>
            </div>
            <div class="myOrder">
              <p class="head">Your Order</p>
              <div class="myOrderBox">
                <div class="orderHead">
                  <p class="name">Product</p>
                  <p class="name">Subtotal</p>
                </div>
                <hr />
                <div class="productPriceDetails">
                  <div class="nameDetails">
                    <img src="" alt="" />
                    <p>Polo Shirt 3D Design -</p>
                    <p>x {{ quantity }}</p>
                  </div>
                  <div class="detailsAmount">
                    <p><span>&#2547;</span></p>
                    <p>{{ totalAmount }}</p>
                  </div>
                </div>
                <hr />
                <div class="productPriceDetails">
                  <p>Subtotal</p>
                  <div class="detailsAmount">
                    <p><span>&#2547;</span></p>
                    <p>{{ totalAmount }}</p>
                  </div>
                </div>
                <hr />
                <div class="productPriceDetails">
                  <p>Shipping</p>
                  <div class="detailsAmount">
                    <p><span>&#2547;</span></p>
                    <p>{{ shippingPrice }}</p>
                  </div>
                </div>
                <div v-if="deliveryCheck" class="productPriceDetails">
                  <p>bKash Charge</p>
                  <div class="detailsAmount">
                    <p><span>&#2547;</span></p>
                    <p>{{ bkashPrice.toFixed(2) }}</p>
                  </div>
                </div>
                <hr />
                <div class="productPriceDetails">
                  <p class="total">Total</p>
                  <div class="detailsAmount">
                    <p class="total"><span>&#2547;</span></p>
                    <p class="total">
                      {{ deliveryCheck ? (totalAmount + bkashPrice + shippingPrice).toFixed(2):(totalAmount + shippingPrice).toFixed(2) }}
                    </p>
                  </div>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
     <div v-if="showModal">
      <ChooseModalVue :price=this.price @dataGet="getData"/>
     </div>
    </div>
  </div>
  <PaymentSectionVue :totalAmount="deliveryCheck ? (totalAmount + bkashPrice + shippingPrice).toFixed(2):(totalAmount + shippingPrice).toFixed(2)" @testCheck="checkBoxCheck"/>
</template>

<script>
import ChooseModalVue from './ChooseModal.vue';
import PaymentSectionVue from './PaymentSection.vue';
export default {
  name: "SingleProductAppCustomerInfo",
  components:{ChooseModalVue,PaymentSectionVue},
  data() {
    return {
      showModal:false,
      quantity: 1,
      price: 900,
      totalAmount: 900,
      districts: [
        { name: "Dhaka", shipping: 80, id: 1 },
        { name: "Saver", shipping: 80, id: 2 },
        { name: "Mymensingha", shipping: 100, id: 3 },
        { name: "Jamalpur", shipping: 150, id: 4 },
        { name: "Dinajpur", shipping: 130, id: 5 },
      ],
      role: "Dhaka",
      shippingPrice: 80,
      bkashPrice: 18,
      size:'M',
      color:'Red',
      deliveryCheck:true,
    };
  },

  mounted() {},
  
  methods: {
    increaseQuan() {
      this.quantity = parseInt(this.quantity) + 1;
      this.totalAmount = this.price * this.quantity;

      const charge = this.totalAmount / 100;
      const totalCharge = charge * 1.8;
      if (totalCharge < 18) {
        return (this.bkashPrice = 18);
      } else {
        return (this.bkashPrice = totalCharge);
      }
    },
    decreaseQuan() {
      if (this.quantity > 1) {
        this.quantity = this.quantity - 1;
        this.totalAmount = this.totalAmount - 900;
      }
      const charge = this.totalAmount / 100;
      const totalCharge = charge * 1.8;
      if (totalCharge < 18) {
        return (this.bkashPrice = 18);
      } else {
        return (this.bkashPrice = totalCharge);
      }
    },
    nameHandle(name) {
      const updateItem = this.districts.filter((item) => {
        if (item.name === name) {
          return item;
        }
        return;
      });
      console.log(JSON.stringify(updateItem));
      updateItem.map((it) => (this.shippingPrice = it.shipping));
    },
    getData(value1,value2){
      console.log(value1,value2)
      if(value1 === 'Choose an option' || value2 === 'Choose an option'){
        this.size = 'M';
        this.color = 'Red';
      }
      else{
        this.size = value1;
      this.color = value2;
      }
      this.showModal = ! this.showModal
    },
    checkBoxCheck(test){
      this.deliveryCheck = !this.deliveryCheck;
    }
  },
};
</script>

<style>
.customer {
  margin-top: 100px;
  margin-bottom: 50px;
  background: #ffffff;
}
.customer .heading {
  margin-bottom: 50px;
  display: flex;
  justify-content: space-between;
}
.customer .heading .name {
  font-family: "Inter";
  font-style: normal;
  font-weight: 500;
  font-size: 24px;
  color: #000000;
}
.customer .heading .account {
  font-family: "Inter";
  font-style: normal;
  font-weight: 400;
  font-size: 18px;
  color: #000000;
}
.customer .shipping .title {
  font-family: "Inter";
  font-style: normal;
  font-weight: 400;
  font-size: 24px;
  color: #000000;
  margin-left: 10px;
  margin-top: 60px;
  margin-bottom: 40px;
}
.customer .shipping .field {
  margin-bottom: 20px;
}
.customer .field label,
.emailField label {
  font-family: "Inter";
  font-style: normal;
  font-weight: 400;
  font-size: 18px;
  color: #000000;
  margin-left: 5px;
}
.customer .field input,
.emailField input,
.customer .field select {
  height: 50px;
  width: 100%;
  padding-left: 20px;
  background: #ffffff;
  box-shadow: 0px 0px 25px rgba(222, 169, 11, 0.6);
  border-radius: 4px;
  border: none;
}

.countries .head .country {
  font-family: "Inter";
  font-style: normal;
  font-weight: 400;
  font-size: 18px;
  line-height: 200%;
  color: #000000;
  margin: 0;
  margin-left: 10px;
  margin-top: 50px;
}
.countries .head .name {
  font-family: "Inter";
  font-style: normal;
  font-weight: 400;
  font-size: 24px;
  color: #000000;
  margin: 0;
  padding: 0;
  margin-left: 10px;
  margin-bottom: 50px;
}

.customer .order .name {
  font-family: "Inter";
  font-style: normal;
  font-weight: 400;
  font-size: 24px;
  color: #000000;
  margin: 0;
  padding: 0;
  margin-left: 10px;
}
.customer .order .mainBox {
  width: 100%;
  height: 250px;

  background: #ffffff;
  box-shadow: 0px 0px 25px rgba(222, 169, 11, 0.6);
  border-radius: 4px;
}
.customer .order .mainBox hr,
.myOrder hr,
hr {
  margin: 0;
  padding: 0;
}
.customer .order .mainBox .orderBox {
  padding: 20px;
  display: flex;
  justify-content: space-around;
}
.customer .order .orderBox .productQuantity,
.customer .order .orderBox .price {
  font-size: 18px;
  display: flex;
}
.customer .order .orderBox .productQuantity .product {
  margin-right: 50px;
}
.customer .poloName {
  margin: 0;
  padding: 0;
  padding-top: 20px;
  padding-left: 20px;
  font-size: 20px;
  font-family: "Inter";
  font-style: normal;
}

.order .select {
  margin-left: 20px;
  padding: 10px;
}
.order .select .checkBox{
  margin-right: 10px;
  
}
.order .select,
.select .addQuantity,
.select .amount {
  display: flex;
  justify-content: start;
  align-items: center;
}
.select .addQuantity button {
  height: 25px;
  width: 25px;
  background-color: transparent;
  border: none;
  border-radius: 4px;
  display: flex;
  text-align: center;
  align-items: center;
}
.select .addQuantity input {
  width: 100px;
  border: 1px solid gray;
  border-radius: 5px;
  outline: none;
  padding-left: 30px;
  padding-right: 30px;
}
.select .addQuantity .minus {
  position: relative;
  left: 26px;
  bottom: 9px;
  cursor: pointer;
}
.select .addQuantity .minus:hover {
  background: rgb(229, 227, 227);
}
.select .addQuantity .plus {
  position: relative;
  right: 26px;
  bottom: 9px;
  cursor: pointer;
}
.select .addQuantity .plus:hover {
  background: rgb(229, 227, 227);
}
.customer .variation {
  margin: 0;
  padding: 0;
  padding-left: 55px;
  font-size: 20px;
  font-family: "Inter";
  font-style: normal;
  color: rgb(246, 68, 68);
}
.customer .variation .modalShow {
 cursor: pointer;
}
.customer .myOrder .myOrderBox {
  min-height: 400px;
  width: 100%;
  padding-left: 20px;
  background: #ffffff;
  box-shadow: 0px 0px 25px rgba(222, 169, 11, 0.6);
  border-radius: 4px;
  border: none;
}
.customer .myOrder {
  margin-top: 40px;
}
.customer .myOrder .head {
  font-family: "Inter";
  font-style: normal;
  font-weight: 400;
  font-size: 24px;
  color: #000000;
  margin: 0;
  padding: 0;
  margin-left: 10px;
}
.customer .myOrder .orderHead .name {
  margin: 0;
  padding: 0;
  font-size: 18px;
}
.customer .myOrder .orderHead,
.myOrder .productPriceDetails {
  padding: 20px;
  display: flex;
  justify-content: space-between;
}
.myOrder .nameDetails,
.myOrder .detailsAmount {
  display: flex;
}
.myOrder .productPriceDetails p {
  margin: 0;
  padding: 0;
  padding-right: 5px;
}
.myOrder .productPriceDetails .total {
  font-family: "Inter";
  font-style: "normal";
  font-size: 22px;
  font-weight: bold;
  padding: 10px;
}
</style>