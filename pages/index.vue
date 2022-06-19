<template>
  <div class="content">
    <div class="content__head head">
      <div class="head__text">
        <div class="head__title">
          {{ $t('home.meName') }}
        </div>
        <div class="head__description">
          {{ $t('home.meInfo') }}
        </div>
      </div>
      <img
        class="head__image"
        src="~assets/img/background/main_pc.png"
      >
    </div>
    <div class="content__block content__block_gray block">
      <div class="block__info">
        <div class="block__title">
          {{ $t('header.aboutMe') }}
        </div>
        <div class="block__description">
          <div class="block__text">
            {{ $t('aboutMe.classic.first') }}
          </div>
          <div class="block__text">
            {{ $t('aboutMe.classic.second') }}
          </div>
          <div class="block__text">
            {{ $t('aboutMe.classic.last') }}
          </div>
        </div>
      </div>
    </div>
    <div class="content__block block">
      <div class="block__info">
        <div class="block__title">
          {{ $t('header.skills') }}
        </div>
        <div class="block__description">
          I work in such programs as
        </div>
        <div class="block__skills">
          <div
            v-for="(skill, key) in skills"
            :key="key"
            class="block__skill skill"
          >
            <img
              class="skill__img"
              :src="skill.img"
              :alt="skill.name"
            >
            <div class="skill__title">
              {{ skill.name }}
            </div>
          </div>
        </div>
      </div>
    </div>
    <div class="content__block content__block_gray block">
      <div class="block__info">
        <div class="block__title">
          {{ $t('header.portfolios') }}
        </div>
        <div class="block__description">
          123123123
        </div>
      </div>
    </div>
    <div class="content__block content__block_last block">
      <div class="block__info">
        <div class="block__title">
          {{ $t('header.contacts') }}
        </div>
        <div class="block__description">
          <div class="block__text">
            Want to know more or just chat?<br>
            You are welcome!
          </div>
        </div>
        <button
          type="button"
          class="block__btn"
          href="mailto:alexbessmelcev@gmail.com"
        >
          Send message
        </button>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  name: 'Main',
  computed: {
    skills() {
      return [
        {
          img: this.Require('skills/Vue.svg'),
          name: this.$t('skills.vue'),
        },
        {
          img: this.Require('skills/Nuxt.svg'),
          name: this.$t('skills.nuxt'),
        },
        {
          img: this.Require('skills/PHP.svg'),
          name: this.$t('skills.php'),
        },
      ];
    },
  },
};
</script>

<style lang="scss" scoped>
.content {
  width: 100%;
  display: flex;
  flex-direction: column;
  align-items: center;
  &__head {
    @include container;
    display: grid;
    padding-bottom: 100px;
  }
  &__block {
    width: 100%;
    padding: 10% 0;
    &_gray {
      background: #F6F6F6;
    }
    &_last {
      padding: 10% 0 5% 0;
    }
  }
}
.head {
  &__image {
    width: 100%;
  }
  &__text {
    display: grid;
    grid-template-columns: 30% 180px;
    justify-content: space-between;
  }
  &__title {
    font-family: 'Gilroy-Bold';
    font-size: 60px;
  }
  &__description {
    font-family: 'Gilroy-Medium';
    font-size: 18px;
    display: flex;
    align-items: flex-end;
    padding-bottom: 20px;
    justify-content: flex-end;
  }
  @include _1199 {
    &__title {
      font-size: 40px;
    }
  }
  @include _767 {
    &__title {
      font-size: 30px;
    }
  }
  @include _575 {
    &__title {
      font-size: 18px;
    }
  }
}
.block {
  &__title {
    font-family: 'Gilroy-Bold';
    font-size: 32px;
  }
  &__description {
    display: grid;
    grid-gap: 20px;
    font-family: 'Gilroy-Medium';
    font-size: 18px;
  }
  &__text {
    text-align: center
  }
  &__btn {
    width: 130px;
    height: 40px;
    border-radius: 20px;
    background-color: black;
    color: white;
  }
  &__info {
    display: grid;
    justify-items: center;
    grid-gap: 20px;
  }
  &__skills {
    display: grid;
    grid-template-columns: repeat(3, 120px);
    grid-gap: 50px;
    align-items: center;
  }
  &__skill {
    display: grid;
    justify-items: center;
    grid-gap: 20px;
  }
}
.skill {
  &__img {
    height:120px;
  }
  &__title {
    font-family: 'Gilroy-Medium';
    font-size: 18px;
  }
}
</style>
