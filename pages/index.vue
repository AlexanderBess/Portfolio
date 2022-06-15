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
    <div class="content__block content__block_gray block">
      <div class="block__info">
        <div class="block__title">
          About me
        </div>
        <div class="block__description">
          <div class="block__text">
            Hi, I'm Alex – Frontend developer from Tomsk.<br>
            I'm interested in design and everything connected with it.
          </div>
          <div class="block__text">
            I'm studying at courses "Web and mobile design<br>
            interfaces" in IT-Academy.
          </div>
          <div class="block__text">
            Ready to implement excellent projects<br>
            with wonderful people.
          </div>
        </div>
      </div>
    </div>
    <div class="content__block block">
      <div class="block__info">
        <div class="block__title">
          Skills
        </div>
        <div class="block__description">
          I work in such programs as
        </div>
        <div class="block__skills">
          123123123
        </div>
      </div>
    </div>
    <div class="content__block content__block_gray block">
      <div class="block__info">
        <div class="block__title">
          Portfolios
        </div>
        <div class="block__description">
          123123123
        </div>
      </div>
    </div>
    <div class="content__block block">
      <div class="block__info">
        <div class="block__title">
          Contacts
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
        >
          Submit
        </button>
      </div>
    </div>
  </div>
</template>
<script>
export default {

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
}
</style>
