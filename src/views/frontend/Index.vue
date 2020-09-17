<template>
  <main>
    <section class="banner text-white">
      <div class="bannerContain mx-auto">
        <div class="d-flex align-items-center justify-content-around">
          <div>
            <div class="titleName mb-3">頂級工藝．先進技術</div>
            <div class="bannerText d-none d-lg-block mb-3">
              來自台灣的專業技師製作，難以抗拒的共鳴音色
              <br />多種入門至進階款式，找到練琴的最佳手感
            </div>
            <router-link to="/products" class="btn border border-primary text-primary bannerBtn">
              挑選你的吉他
              <span>
                <i class="fas fa-angle-right"></i>
              </span>
            </router-link>
          </div>
          <div>
            <div class="guitarBox mx-auto"></div>
            <div class="guitarShadow">
              <img src="@/assets/images/frontend/index/shadow.png" class="img-fluid" />
            </div>
          </div>
        </div>
      </div>
    </section>
    <section class="py-5 productHeight">
      <div class="productBox mx-auto">
        <div class="text-center text-lg-left">
          <div class="titleName">產品介紹</div>
          <div class="subName ml-lg-5">Product Description</div>
        </div>
        <div class="position-relative text-primary text-center d-lg-flex justify-content-between">
          <router-link to="/products" tag="div" class="productItem product_ele">
            <div class="position-relative">
              <img src="@/assets/images/frontend/index/product_ele.jpg" class="img-fluid" />
              <div class="productName">
                <span class="productBorder">電吉他</span>
              </div>
            </div>
          </router-link>
          <router-link to="/products" tag="div" class="productItem product_wood">
            <div class="position-relative">
              <img src="@/assets/images/frontend/index/product_wood.jpg" class="img-fluid" />
              <div class="productName">
                <span class="productBorder">木吉他</span>
              </div>
            </div>
          </router-link>
          <router-link to="/products" tag="div" class="productItem product_ukulele">
            <div class="position-relative">
              <img src="@/assets/images/frontend/index/product_ukulele.jpg" class="img-fluid" />
              <div class="productName">
                <span class="productBorder">烏克莉莉</span>
              </div>
            </div>
          </router-link>
        </div>
      </div>
    </section>
    <!--
    <section class="py-5">
      <div class="productBox mx-auto">
        <div class="text-center text-lg-left">
          <div class="titleName">精選樂器</div>
          <div class="subName ml-lg-5">Chosen Instrument</div>
        </div>
      </div>
      <superslide :options="options" class="overflow-hidden text-primary">
        <div class="bd">
          <ul class="d-flex list-unstyled">
            <li>
              <div class="grayBg">
                <div class="chosenImg">
                  <img src="@/assets/images/frontend/index/p1.png" class="img-fluid" />
                  <div>Awime x19</div>
                </div>
              </div>
            </li>
            <li>
              <div class="grayBg">
                <div class="chosenImg">
                  <img src="@/assets/images/frontend/index/p2.png" class="img-fluid" />
                  <div>Awime x19</div>
                </div>
              </div>
            </li>
            <li>
              <div class="grayBg">
                <div class="chosenImg">
                  <img src="@/assets/images/frontend/index/p3.png" class="img-fluid" />
                  <div>Awime x19</div>
                </div>
              </div>
            </li>
            <li>
              <div class="grayBg">
                <div class="chosenImg">
                  <img src="@/assets/images/frontend/index/p4.png" class="img-fluid" />
                  <div>Awime x19</div>
                </div>
              </div>
            </li>
            <li>
              <div class="grayBg">
                <div class="chosenImg">
                  <img src="@/assets/images/frontend/index/p5.png" class="img-fluid" />
                  <div>Awime x19</div>
                </div>
              </div>
            </li>
            <li>
              <div class="grayBg">
                <div class="chosenImg">
                  <img src="@/assets/images/frontend/index/p4.png" class="img-fluid" />
                  <div>Awime x19</div>
                </div>
              </div>
            </li>
            <li>
              <div class="grayBg">
                <div class="chosenImg">
                  <img src="@/assets/images/frontend/index/p5.png" class="img-fluid" />
                  <div>Awime x19</div>
                </div>
              </div>
            </li>
          </ul>
        </div>
        <div class="hd mt-5">
          <ul class="list-unstyled d-flex justify-content-center"></ul>
        </div>
      </superslide>
    </section>
    -->
  </main>
</template>
<script>
export default {
  data() {
    return {
      options: {
        mainCell: '.bd ul',
        titCell: '.hd ul',
        autoPlay: true,
        autoPage: true,
        effect: 'leftLoop',
        scroll: 5,
        vis: 5,
      },
    };
  },
  methods: {},
};
</script>
<style lang="scss" scoped>
/*BANNER*/
.banner {
  background-image: url("~@/assets/images/frontend/index/banner.jpg");
  background-repeat: no-repeat;
  background-size: cover;
  height: 80vw;
  max-height: 1500px;
}
.bannerContain {
  width: 90%;
  max-width: 1300px;
}
.bannerBtn {
  background-color: rgba(0, 0, 0, 0.5);
  font-size: 0.8rem;
}
.guitarBox {
  background-image: url("~@/assets/images/frontend/index/guitar1.png");
  background-repeat: no-repeat;
  background-size: cover;
  background-position-y: bottom;
  height: 62vw;
  max-width: 400px;
  max-height: 900px;
}
.guitarShadow {
  width: 30vw;
  max-width: 450px;
}
.bannerText {
  line-height: 2.5rem;
  font-size: 1rem;
}
@media screen and (min-width: 992px) {
  .bannerBtn {
    font-size: 1rem;
  }
}
/*BANNER END*/
/*PRODUCT*/
.productHeight {
  height: 180vw;
}
.productItem {
  width: 48%;
  position: absolute;
  overflow: hidden;
  cursor: pointer;
}
.productBox {
  width: 90%;
}
.product_ele {
  top: 0;
  left: 0;
}
.product_wood {
  top: 25vw;
  right: 0;
}
.product_ukulele {
  top: 75vw;
  left: 10vw;
}
.productName {
  position: absolute;
  bottom: 0;
  background-color: rgba(0, 0, 0, 0.7);
  width: 100%;
  padding: 0.5rem 0;
}
@media screen and (min-width: 992px) {
  .productHeight {
    height: auto;
  }
  .productItem {
    width: 33%;
    position: initial;
    &:hover {
      .productName {
        display: flex;
      }
      img {
        transition: all 0.4s ease-in-out;
        transform: scale(1.2);
      }
    }
  }
  .productName {
    height: 100%;
    display: none;
    justify-content: center;
    align-items: center;
    font-size: 1.2rem;
  }
  .productBorder {
    border: 1px solid;
    padding: 1.5rem 3rem;
  }
}
/*PRODUCT END*/
/*Chosen Instrument*/
.bd li {
  width: 100%;
}
.grayBg {
  background-color: #313131;
  border: 1px #707070 solid;
  border-radius: 0.5rem;
  width: 370px;
  height: 23vw;
  position: relative;
  margin: 0 5px;
  img {
    padding: 0 0.5rem;
    transform: rotate(15deg);
  }
}
.chosenImg {
  position: absolute;
  bottom: 5px;
  left: 20%;
  font-size: 0.8rem;
}
::v-deep .hd {
  li {
    background-color: rgba(255,255,255,.3);
    width: 10px;
    height: 10px;
    border-radius: 100%;
    margin: 5px;
    text-indent: -999px;
    &.on {
      background-color: rgba(255,255,255, 1);
    }
  }
}
/*Chosen Instrument END*/
</style>
