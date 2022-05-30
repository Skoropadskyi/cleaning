<template>
  <div class="list">
    <div class="list__block">
      <div
        class="list__item"
        v-for="(list, i) in lists"
        :key="i"
        @click="change"
      >
        <h5>{{ list.title }}</h5>
      </div>
    </div>
    <div class="image" v-for="(image, id) in lists" :key="id">
      <transition name="mode-fade" mode="out-in">
        <img
          v-if="cleanTitle === lists[id].title"
          :src="require(`@/assets/image/${image.image}.png`)"
          alt="Foto"
        />
      </transition>
    </div>
  </div>
</template>

<script>
export default {
  // eslint-disable-next-line vue/multi-word-component-names
  name: "List",
  data() {
    return {
      cleanTitle: "Кухня",
      lists: [
        {
          title: "Кухня",
          image: "kitch",
        },
        {
          title: "Комнаты",
          image: "kitch",
        },
        {
          title: "Ванная",
          image: "bathroom",
        },
        {
          title: "Прихожая",
          image: "bathroom",
        },
      ],
    };
  },
  methods: {
    change(title) {
      this.cleanTitle = title.target.innerHTML;
    },
  },
};
</script>

<style scoped lang="scss">
.list {
  height: 100vh;
  display: flex;
  justify-content: space-between;
  padding-top: 142px;
  &__block {
    min-width: 380px;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    background: #5a30f0;
  }
  &__item {
    cursor: pointer;
    padding-bottom: 22px;
    h5 {
      font-style: normal;
      font-weight: 400;
      font-size: 44px;
      line-height: 120%;
      text-align: left;
      color: #ffffff;
      opacity: 0.7;
    }
    h5:hover {
      font-style: italic;
      font-weight: 400;
      font-size: 44px;
      line-height: 120%;
      color: #ffffff;
      opacity: 1;
    }
  }
  .image {
    img {
      display: block;
      width: 100vw;
      height: 100vh;
      object-fit: cover;
    }
  }
}
.mode-fade-enter-active,
.mode-fade-leave-active {
  transition: opacity 0.5s ease;
  opacity: 0;
}

.mode-fade-enter-from,
.mode-fade-leave-to {
  opacity: 0;
}
</style>
