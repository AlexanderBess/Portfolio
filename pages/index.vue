<template>
  <div class="content">
    <div class="content__head head">
      <div class="head__text">
        <div class="head__title">
          Aleksandr Bessmeltsev
        </div>
        <div class="head__description">
          Frontend developer<br>22 years old, Tomsk
        </div>
      </div>
      <img
        class="head__image"
        src="~assets/img/background/main_pc.png"
      >
    </div>
    <div class="content__blocks">
      123
    </div>
  </div>
</template>
<script>
export default {

};
</script>

<style lang="scss" scoped>
.content {
  @include container;
  &__head {
    display: grid;
    padding-bottom: 100px;
  }
}
.head {
  &__image {
    width: 100%;
  }
  &__text {
    display: grid;
    grid-template-columns: 30% auto;
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
</style>
