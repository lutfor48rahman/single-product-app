<template>
  <div class="payment">
    <div class="container">
      <div class="heading">
        <p>Payment</p>
      </div>
      <div class="paymentContent">
        <div class="title">
          <p>bKash</p>
          <img :src="logo" alt="" />
        </div>
        <div class="paymentMainContent">
          <div class="paymentPoint">
            <p>
              &#8658; মোবাইল কি পেডে <span>*247#</span> ডায়াল করুন অথবা বিকাশ এপ ব্যবহার করে উপরে উল্লেখিত Total এমাউন্ট সেন্ড মানি করুন.
            </p>
            <p>
              &#8658; তারপর মোবাইল মেসেজে আসা ট্রান্জেকশন কোডটি ও যে নাম্বার থেকে সেন্ড করলেন সেটি নিচের ইনপুট বক্সে লিখে অর্ডার সাবমিট করে দিন.
            </p>
          </div>
          <div class="paymentHints">
            <p>bKash "Send Money" fee will be added with net price.</p>
          </div>
          <div class="remainderPayment">
            <p><small>You need to send us &#2547; {{totalAmount}}</small></p>
          </div>
          <div class="paymentNumber">
            <p>Payment Type: Personal</p>
            <p>Payment Number: 018******78</p>
          </div>
          <div class="paymentInput">
            <div class="paymentField">
              <label>Your bKash Account Number</label> <br />
              <input type="text" />
            </div>
            <div class="paymentField">
              <label>Your Transaction ID</label>
              <br />
              <input type="text" />
            </div>
            <div class="paymentSelect">
             <div>
              <p><input type="checkbox" v-model="testCheckBox" @click="yesOrno"/></p>
              <span class="checkmark"></span>
             </div>
              <div>
                <p class="checkTitle">Cash on delivery</p>
              </div>
            </div>
          </div>
        </div>
      </div>
      <div class="paymentFooterText">
        <p>
            Your personal data will be used to process your order, support your experience throughout this website, and for other purposes
            described in our <span>privacy policy</span>.
            
        </p>
      </div>
      <div class="paymentCheckout">
        <p><img :src="icon" alt="" /></p>
        <p class="checkOrder">Place Order &#2547; {{totalAmount}}</p>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "ProductPaymentSection",

  data() {
    return {
      logo: "https://i.ibb.co/9YVMg17/image-6.png",
      icon: "https://i.ibb.co/RSV08qF/Group-8.png",
      testCheckBox:false,
    };
  },
  props:['totalAmount'],
  mounted() {
    
  },
  
setup(){
    
},
  methods: {
    yesOrno(){
        this.$emit('testCheck', this.testCheckBox);
    },
  },
};
</script>

<style>
.payment .heading {
  font-family: "Inter";
  font-style: normal;
  font-weight: 500;
  font-size: 24px;
  line-height: 200%;
  color: #000000;
}
.payment .paymentMainContent {
  padding: 20px;
}
.payment .paymentContent {
  background: #ffffff;
  border: 1px solid #dea90b;
  box-shadow: 0px 0px 25px rgba(222, 169, 11, 0.6);
  border-radius: 4px;
}

.paymentContent .title {
  margin: 0;
  padding: 0;
  border-bottom: 1px solid #dea90b;
}
.paymentContent .title {
  padding-left: 20px;
  padding-right: 20px;
}
.paymentContent .title p {
  font-family: "Inter";
  font-style: normal;
  font-weight: 400;
  font-size: 24px;
  line-height: 200%;
  color: #e3106e;
}
.paymentContent .title img {
  width: 33px;
  height: 33px;
}
.paymentContent .title {
  display: flex;
  justify-content: space-between;
  align-items: center;
}
.paymentContent .paymentPoint {
  margin-top: 30px;
}
.paymentContent .paymentPoint span{
  color:  #E3106E;
}
.paymentContent .paymentHints p {
  font-family: "Inter";
  font-style: normal;
  font-weight: 400;
  font-size: 24px;
  color: #000000;
}
.paymentContent .remainderPayment p small {
  font-family: "Inter";
  font-style: normal;
  font-weight: 400;
  font-size: 18px;
  color: #00fe0a;
}

.paymentContent .paymentNumber p {
  margin: 0;
  padding: 0;
  font-family: "Inter";
  font-style: normal;
  font-weight: 400;
  font-size: 18px;
  color: #000000;
}
.payment .paymentInput {
  margin-top: 20px;
}
.paymentInput .paymentField label {
  font-family: "Inter";
  font-style: normal;
  font-weight: 400;
  font-size: 18px;
  line-height: 200%;
  color: #000000;
}
.paymentInput .paymentField input {
  width: 384px;
  height: 52px;
  padding-left: 20px;
  background: #f6edf7;
  border: 1px solid #dea90b;
}
.paymentInput .paymentSelect {
  margin-top: 20px;
  display: flex;
  align-items: center;
}
.paymentInput .paymentSelect p input {
  width: 26px;
  height: 26px;
  border-radius: 50%;
  vertical-align: middle;
  border: 1px solid #ddd;
  background: #ffffff;
  box-shadow: inset 0px 0px 6px rgba(0, 0, 0, 0.25);
  appearance: none;
  -webkit-appearance: none;
  outline: none;
  cursor: pointer;
}
.paymentInput .paymentSelect p input:checked {
	background: #dea90b;
}
.paymentSelect .checkmark{
  position: absolute;
  top: 9px;
	left: 9px;
	width: 8px;
	height: 8px;
	border-radius: 50%;
  background: #dea90b;
}
.paymentInput .paymentSelect .checkTitle {
  font-family: "Inter";
  font-style: normal;
  font-weight: 500;
  font-size: 20px;
  color: #000000;
  margin-left: 20px;
}
.payment .paymentFooterText {
  margin: 20px;
}
.payment .paymentFooterText p {
  font-family: "Inter";
  font-style: normal;
  font-weight: 500;
  font-size: 18px;
  line-height: 200%;
  color: #000000;
}
.payment .paymentFooterText p span{
  color: #DEA90B;
}
.payment .paymentCheckout {
  margin-bottom: 50px;
  height: 70px;
  background: #dea90b;
  box-shadow: 0px 0px 20px rgba(222, 169, 11, 0.6);
  border-radius: 4px;
  display: flex;
  justify-content: center;
  align-items: center;
  cursor: pointer;
}
.payment .paymentCheckout img {
    height: 20px;
}
.payment .paymentCheckout .checkOrder {
  font-family: "Inter";
  font-style: normal;
  font-weight: 600;
  font-size: 30px;
  color: #e3106e;
  margin-left: 10px;
}




</style>