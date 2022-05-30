<template>
  <div class="intro">
    <div class="intro__inner">
      <div class="intro__inner-picture"></div>
      <div class="intro__inner-text">
        <h1 class="title">Уборка квартир в Киеве</h1>
        <p class="subtitle">
          Мы уберем у вас дома или в офисе. Наведем чистоту после ремонта и
          проведем генеральную уборку.
        </p>
      </div>
    </div>
    <div class="btn" :class="!ifScroll ? true : 'fixed'">
      <span
        >Заказать <br />
        уборку</span
      >
    </div>
  </div>
</template>

<script>
export default {
  // eslint-disable-next-line vue/multi-word-component-names
  name: "Intro",
  data() {
    return {
      ifScroll: false,
    };
  },
  methods: {
    scrollHandle(e) {
      let top = e.srcElement.scrollingElement.scrollTop; // Получить высоту прокрутки страницы
      if (top < 10) {
        this.ifScroll = false;
      } else if (top >= 10 && top < 1800) {
        this.ifScroll = true;
      } else if (top > 1800) {
        this.ifScroll = false;
      }
    },
  },
  mounted() {
    window.addEventListener("scroll", this.scrollHandle);
  },
};
</script>

<style scoped lang="scss">
.intro__inner {
  display: flex;
  align-items: center;
  &-picture {
    width: 50%;
    height: 100vh;
    position: relative;
    max-width: 1100px;
    background: url(../assets/image/intro_back.png) center no-repeat;
    background-size: cover;
    img {
      max-width: 100%;
      min-width: 400px;
    }
  }
  &-text {
    max-width: 380px;
    text-align: left;
    margin: 0 auto;
    .title {
      font-style: normal;
      font-weight: 400;
      font-size: 76px;
      line-height: 110%;
      color: #404040;
    }
    .subtitle {
      font-style: normal;
      font-weight: 400;
      font-size: 18px;
      line-height: 140%;
      color: #404040;
    }
  }
}
.btn {
  position: absolute;
  background: #5a30f0;
  border: 1px solid rgba(255, 255, 255, 0.1);
  bottom: 0;
  left: 45%;
  border-radius: 50%;
  padding: 50px 22px;
  margin-bottom: 20px;
  cursor: pointer;
  z-index: 1;
  animation: spin 5s linear 0s infinite;

  span {
    font-style: normal;
    font-weight: 500;
    font-size: 18px;
    line-height: 130%;
    display: flex;
    align-items: center;
    text-align: center;
    letter-spacing: 0.03em;
    text-transform: uppercase;
    color: #ffffff;
    transform: rotate(-15deg);
  }
}
@keyframes spin {
  from {
    transform: rotate(0deg);
  }
  to {
    transform: rotate(360deg);
  }
}
</style>
