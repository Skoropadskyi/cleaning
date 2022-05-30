<template>
  <div id="app">
    <nav :class="!ifScroll ? true : 'fixed'">
      <div class="header">
        <div class="header__left">
          <a href="/"><img src="../src/assets/logo.svg" alt="Logo" /></a>
          <div class="button" id="button-switch">
            <input type="checkbox" class="checkbox" />
            <div class="knobs">
              <span>Дом</span>
            </div>
            <div class="layer"></div>
          </div>
        </div>

        <div class="header__right">
          <div class="header__right-links">
            <a href="/">После ремонта</a>
            <a href="/">Генеральная уборка</a>
            <a href="/">Регулярная уборка</a>
            <a href="/">Мойка окон</a>
          </div>
          <div class="header__right-tel">
            <a href="tel:+380 67 401 69 77">+380 67 401 69 77</a>
            <span> | 24/7</span>
          </div>
          <div class="header__right-hambur">
            <img src="../src/assets/menu.svg" alt="Menu" />
          </div>
        </div>
      </div>
    </nav>
    <router-view />
  </div>
</template>

<script>
export default {
  data() {
    return {
      ifScroll: false,
    };
  },
  methods: {
    scrollHandle(e) {
      let top = e.srcElement.scrollingElement.scrollTop; // Получить высоту прокрутки страницы
      if (top < 50) {
        this.ifScroll = false;
      } else if (top >= 50 && top < 2200) {
        this.ifScroll = true;
      } else if (top > 2200) {
        this.ifScroll = false;
      }
    },
  },
  mounted() {
    window.addEventListener("scroll", this.scrollHandle);
  },
};
</script>

<style lang="scss">
* {
  margin: 0;
}
#app {
  font-family: TTTravels, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  overflow: hidden;
}

.fixed {
  position: fixed !important;
  background: #ffffff;
  box-shadow: 0 2px 14px rgba(0, 0, 0, 0.07);
}

nav {
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  z-index: 10;
  width: 100%;
  a {
    font-style: normal;
    font-weight: 500;
    font-size: 16px;
    line-height: 120%;
    letter-spacing: 0.2px;
    color: #404040;
    text-decoration: none;
  }

  .header {
    display: flex;
    align-items: center;
    justify-content: space-between;
    padding: 16px 30px 16px 54px;
    &__left,
    &__right {
      display: flex;
      align-items: center;
    }
    &__right {
      &-links {
        a {
          padding-right: 32px;
        }
        a:last-child {
          padding-right: 0;
        }
      }
      &-tel {
        padding: 0 32px 0 67px;
      }
    }
  }
}

.knobs,
.layer {
  position: absolute;
  top: 0;
  right: 0;
  bottom: 0;
  left: 0;
}

.button {
  position: relative;
  width: 131px;
  height: 37px;
  margin-left: 20px;
  overflow: hidden;
}

.button.r,
.button.r .layer {
  border-radius: 100px;
}

.checkbox {
  position: relative;
  width: 100%;
  height: 100%;
  padding: 0;
  margin: 0;
  opacity: 0;
  cursor: pointer;
  z-index: 3;
}

.knobs {
  z-index: 2;
}

.layer {
  width: 100%;
  box-sizing: border-box;
  background: #ffffff;
  border: 1px solid #e2e8f0;
  border-radius: 48px;
  transition: 0.6s ease all;
  z-index: 1;
}

/* Button-Switch */
#button-switch .knobs:before,
#button-switch .knobs:after,
#button-switch .knobs span {
  position: absolute;
  width: 55px;
  height: 31px;
  font-weight: 500;
  font-size: 14px;
  line-height: 110%;
  text-align: center;
  /*padding: 8px 12px;*/
  margin: 3px;
  transition: 0.6s ease all;
}

#button-switch .knobs:before {
  content: "";
  left: 0;
  background: #5a30f0;
  border-radius: 34px;
}

#button-switch .knobs:after {
  content: "Офис";
  right: 0;
  line-height: 30px;
  color: #636c81;
}

#button-switch .knobs span {
  display: inline-block;
  left: 0;
  line-height: 30px;
  color: #ffffff;
  z-index: 1;
}

#button-switch .checkbox:checked + .knobs span {
  color: #636c81;
}

#button-switch .checkbox:checked + .knobs:before {
  left: 70px;
  background: #5a30f0;
  border-radius: 34px;
}

#button-switch .checkbox:checked + .knobs:after {
  color: #ffffff;
}

#button-switch .checkbox:checked ~ .layer {
  background: #ffffff;
}
</style>
