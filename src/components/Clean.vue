<template>
  <div class="container">
    <div class="clean">
      <div class="clean__text">
        <h2 class="title">Как мы убираем</h2>
        <p class="subtitle">
          Клинер приезжает в назначенное время со всем необходимым и сразу
          приступает к делу. Вам остаётся только оценить результат.
        </p>
      </div>
      <div class="clean__picture"></div>
    </div>
  </div>
</template>

<script>
export default {
  // eslint-disable-next-line vue/multi-word-component-names
  name: "Clean",
};
</script>

<style scoped lang="scss">
.clean {
  padding: 0 170px;
  &__text {
    display: flex;
    justify-content: space-between;
    margin-bottom: 52px;
    .title {
      font-style: normal;
      font-weight: 400;
      font-size: 44px;
      line-height: 120%;
      color: #404040;
    }
    .subtitle {
      max-width: 420px;
      text-align: left;
      font-style: normal;
      font-weight: 400;
      font-size: 18px;
      line-height: 140%;
      color: #404040;
    }
  }
  &__picture {
    width: 100%;
    height: 700px;
    position: relative;
    background: url(../assets/image/kitchen.png) center no-repeat;
    background-size: cover;
  }
}
</style>
