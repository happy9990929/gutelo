<template>
  <nav class="navbar navbar-expand-lg navbar-dark bg-dark pt-lg-3">
      <router-link to="/" class="navbar-brand mx-auto mx-lg-5">
        <img src="@/assets/images/frontend/logo.png" class="navLogo"/>
      </router-link>
      <button
        class="navbar-toggler border-0 position-absolute"
        type="button"
        data-toggle="collapse"
        data-target="#navbarNavAltMarkup"
        aria-controls="navbarNavAltMarkup"
        aria-expanded="false"
        aria-label="Toggle navigation"
      >
        <span class="navbar-toggler-icon"></span>
      </button>
      <div class="collapse navbar-collapse" id="navbarNavAltMarkup">
        <div class="navbar-nav text-center justify-content-lg-between w-100">
          <div class="d-lg-flex">
            <router-link class="nav-link text-primary mx-md-3" to="/about">關於我們</router-link>
            <router-link class="nav-link text-primary mx-md-3" to="/products">產品列表</router-link>
          </div>
          <router-link class="nav-link text-primary mx-md-3 position-relative" to="/cart">
            <span><i class="fas fa-shopping-cart"></i></span>
            <!-- <span class="cartNum bg-danger text-white">{{amount}}</span> -->
          </router-link>
        </div>
      </div>
    </nav>
</template>

<script>
export default {
  data() {
    return {
      cart: [],
      amount: 0,
      cartTotal: 0,
    };
  },
  created() {
    this.getCart();
  },
  methods: {
    getCart() {
      const loader = this.$loading.show();
      const api = `${process.env.VUE_APP_APIPATH}/api/${process.env.VUE_APP_UUID}/ec/shopping`;
      this.$http.get(api).then((res) => {
        loader.hide();
        this.cart = res.data.data;
        this.cartAmount();
      }).catch((error) => {
        loader.hide();
        console.log(error);
      });
    },
    cartAmount() {
      this.amount = this.cart.reduce((acc, val) => acc + val.quantity, 0);
      this.cartTotal = this.cart.reduce((acc, val) => acc + val.product.price * val.quantity, 0);
    },
  },
};
</script>

<style lang="scss" scoped>
.navbar {
  position: fixed;
  width: 100%;
  z-index: 10;
}
.navLogo {
  width: 100px;
}
.navbar-toggler {
  position: absolute;
  top: 10px;
  left: 10px;
  outline: 0;
}
.cartNum {
  position: absolute;
  top: 20px;
  right: -10px;
  width: 30px;
  line-height: 1;
  border-radius: 10px;
  font-size: .8rem;
  padding: 1px;
}
@media screen and (min-width: 992px){
  .navLogo {
    width: 200px;
  }
  .cartNum {
    top: 4px;
  }
}
</style>
