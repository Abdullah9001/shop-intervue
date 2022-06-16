<template>
  <div>
    <div class="conteinerr">
      <div class="cardd">
        <div
          class="card-contentt"
          v-for="(product, index) in Products"
          :key="index"
        >
          <div class="card-img"></div>
          <img class="pimage" :src="product.product_thambnail" />
          <h4>{{ product.product_name }}</h4>
          <p>$:{{ product.selling_price }}</p>
          <p>{{ product.meta_title }}</p>
          <a class="btn" @click="addCart">Add Cart</a>
        </div>
      </div>
    </div>

    <br /><br /><br />
    <hr />
    <br /><br />

    <div class="container">
      <div class="card">
        <div class="car-img">
          <img
            class="cImg"
            src="https://bppshops.com/upload/products/thambnail/1734523914538853.webp"
          />
        </div>

        <div class="plus">
          <h3 class="button" @click="addCart">+</h3>
          <h3>Product: {{ cartCount }}</h3>
          <h3 class="button" @click="removeCart">-</h3>
        </div>
        <h3>Price:{{ cardPrice }}</h3>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      cartCount: 0,
      cardPrice: 0,
    };
  },
  methods: {
    addCart() {
      this.cartCount++;
      this.cardPrice += 70;
    },
    removeCart() {
      if (this.cartCount > 0) {
        this.cartCount--;
        this.cardPrice -= 70;
      }
    },
  },
  computed: {
    Products() {
      return this.$store.state.Products;
    },
  },
};
</script>

<style scoped>
.conteinerr {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
}

h4 {
  font-family: "Lato", sans-serif;
  margin-top: 3px;
  color: #1abc9c;
}

p {
  font-family: "Lato", sans-serif;
  margin-top: 2px;
  color: #1abc9c;
}
.cardd {
  display: flex;
  flex-wrap: wrap;
  justify-content: space-around;
  margin-top: 2rem;
  padding: 2rem;
}

.card-contentt {
  padding: 20px;
  margin-top: 20px;
  border: 1px solid #9b9e9d;
  border-radius: 10px;
}

.card-contentt:hover {
  box-shadow: rgba(0, 0, 0, 0.3) 0px 19px 38px,
    rgba(0, 0, 0, 0.22) 0px 15px 12px;
}

.pimage {
  width: 250px;
  height: 240px;
  border-radius: 20px;

  margin: 3px;
}

.btn {
  color: #1abc9c;
  padding: 8px 20px;
  margin-bottom: 20px;
  border: 1px solid #1abc9c;
  position: relative;
  transition: all 0.3s ease 0s;
}

.btn::after {
  content: "";
  position: absolute;
  top: 0;
  left: 0;
  width: 0%;
  height: 100%;
  background: #1abc9c;
  /* transform: scaleX(0); */
  /* transform-origin: left; */
  transition: all 0.3s ease 0s;
  z-index: -1;
}

.btn:hover {
  cursor: pointer;
  color: #fff;
}

.btn:hover::after {
  width: 100%;
}

span {
  color: #bb0e0e;
}

.conteiner {
  display: flex;
}

.cImg {
  width: 100px;
  height: 100px;
  border: 1px solid #9b9e9d;
}

.card {
  display: flex;
  justify-content: space-around;
  align-items: center;
  text-align: center;
  margin: 3rem 0;
  padding: 1rem;
  background: #1abc9c;
}

.plus {
  display: flex;
  align-content: center;
  text-align: center;
  justify-content: center;
}

.button {
  margin-right: 30px;
  margin-left: 30px;
  cursor: pointer;
  padding: 10px;
}
</style>
