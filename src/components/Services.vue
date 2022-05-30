<template>
  <div class="service">
    <div class="container">
      <div class="card__inner">
        <div class="card">
          <div class="card__side card__side-front">
            <h4 class="card__heading">Тщательно отобранный персонал</h4>
            <img src="../assets/image/personal.png" alt="Personal" />
          </div>

          <div class="card__side card__side-back card__side-back-1">
            <p class="card__text">
              Не нужно тратить время, силы и ресурсы на размещение вакансий,
              проведение собеседований, проверку кандидатов на должность
              уборщицы. За счет больших объемов мы можем сделать это
              эффективнее.
            </p>
          </div>
        </div>

        <div class="card">
          <div class="card__side card__side-front">
            <h4 class="card__heading">Качественная эко-химия</h4>
            <img src="../assets/image/chemistry.png" alt="Chemistry" />
          </div>

          <div class="card__side card__side-back card__side-back-1">
            <p class="card__text">
              Не нужно тратить время, силы и ресурсы на размещение вакансий,
              проведение собеседований, проверку кандидатов на должность
              уборщицы. За счет больших объемов мы можем сделать это
              эффективнее.
            </p>
          </div>
        </div>

        <div class="card">
          <div class="card__side card__side-front">
            <h4 class="card__heading">Контролируем качество</h4>
            <img src="../assets/image/quality.png" alt="Quality" />
          </div>

          <div class="card__side card__side-back card__side-back-1">
            <p class="card__text">
              Не нужно тратить время, силы и ресурсы на размещение вакансий,
              проведение собеседований, проверку кандидатов на должность
              уборщицы. За счет больших объемов мы можем сделать это
              эффективнее.
            </p>
          </div>
        </div>

        <div class="card">
          <div class="card__side card__side-front">
            <h4 class="card__heading">Работаем круглосуточно</h4>
            <img src="../assets/image/phone.png" alt="Phone" />
          </div>

          <div class="card__side card__side-back card__side-back-1">
            <p class="card__text">
              Не нужно тратить время, силы и ресурсы на размещение вакансий,
              проведение собеседований, проверку кандидатов на должность
              уборщицы. За счет больших объемов мы можем сделать это
              эффективнее.
            </p>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  // eslint-disable-next-line vue/multi-word-component-names
  name: "Services",
};
</script>

<style scoped lang="scss">
.service {
  padding: 73px 0 150px;
}
.card__inner {
  display: flex;
  justify-content: space-between;
  padding: 0 60px;
}
.card {
  -webkit-perspective: 150rem;
  perspective: 150rem;
  -moz-perspective: 150rem;
  position: relative;
  height: 328px;
  width: 300px;
  margin-right: 40px;
  .card__side {
    height: 328px;
    -webkit-transition: all 0.8s ease;
    transition: all 0.8s ease;
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    -webkit-backface-visibility: hidden;
    backface-visibility: hidden;
    border-radius: 3px;
    overflow: hidden;
    -webkit-box-shadow: 0 1.5rem 4rem rgb(0 0 0 / 15%);
    box-shadow: 0 1.5rem 4rem rgb(0 0 0 / 15%);
    &-front {
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: space-between;
      background-color: #f3f6fb;
      border-radius: 8px;
      .card__heading {
        font-style: normal;
        font-weight: 500;
        font-size: 24px;
        line-height: 130%;
        text-align: center;
        color: #404040;
        padding: 20px 40px;
      }
    }
    &-back {
      -webkit-transform: rotateY(180deg);
      transform: rotateY(180deg);
      .card__text {
        font-style: normal;
        font-weight: 400;
        font-size: 16px;
        line-height: 140%;
        color: #ffffff;
        text-align: left;
        padding: 30px;
      }
    }
    &-back-1 {
      background: #5a30f0;
      border-radius: 8px;
    }
  }
}
.card:last-child {
  margin-right: 0;
}
.card:hover .card__side-front {
  -webkit-transform: rotateY(-180deg);
  transform: rotateY(-180deg);
}
.card:hover .card__side-back {
  -webkit-transform: rotateY(0);
  transform: rotateY(0);
}
</style>
