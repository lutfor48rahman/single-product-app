<template>
  <div class="faq">
    <div class="container">
      <div class="mainContent">
        <div class="title">
          <p class="name">F.A.Q</p>
          <p class="name2">বিভিন্ন প্রশ্নের উত্তর</p>
        </div>
        <div class="faqAns">
          <div class="questions">
            <details>
              <summary>How do I create accordion?</summary>
              <div>
                The tags <em>details</em> and <em>summary</em> have you covered.
              </div>
            </details>
            <details>
              <summary>How do I create accordion?</summary>
              <div>
                The tags <em>details</em> and <em>summary</em> have you covered.
              </div>
            </details>
            <details>
              <summary>How do I create accordion?</summary>
              <div>
                The tags <em>details</em> and <em>summary</em> have you covered.
              </div>
            </details>
          </div>
          <div class="sapanIcon"></div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "SingleProductAppFAQ",

  data() {
    return {
      img: "https://i.ibb.co/PDfrBBF/image-3.png",
    };
  },

  mounted() {},

  methods: {},
};
</script>

<style>
.faq {
  margin-top: 50px;
  margin-bottom: 50px;
}
.faq .mainContent {
  width: 70%;
  margin: auto;
}
.faq .mainContent .title {
  padding-top: 50px;
  display: flex;
  justify-content: space-between;
}
.faq .mainContent .title .name {
  font-family: "Poppins";
  font-style: normal;
  font-weight: 600;
  font-size: 28px;
  color: #000000;
}
.faq .mainContent .title .name2 {
  font-family: "Poppins";
  font-style: normal;
  font-weight: 500;
  font-size: 20px;
  color: #000000;
}
details {
  font-size: 1.5rem;
  border: 1px solid gray;
  background: #ffffff;
  box-shadow: 0px 0px 12px rgba(0, 0, 0, 0.15);
  border-radius: 4px;
}

summary {
  padding: 0.5em 1.3rem;
  list-style: none;
  display: flex;
  justify-content: space-between;
  transition: height 1s ease;
}

summary::-webkit-details-marker {
  display: none;
}
summary:after {
  content: "\002B";
  border: 1px solid black;
  border-radius: 50%;
  width: 30px;
  display: flex;
  justify-content: center;
  align-items: center;
}

details[open] summary {
  border-bottom: 1px solid #aaa;
  margin-bottom: 0.5em;
}

details[open] summary:after {
  content: "\00D7";
}

details[open] div {
  padding: 0.5em 1em;
}
</style>