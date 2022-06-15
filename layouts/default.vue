<template>
  <div class="primary">
    <div class="primary__template template">
      <div class="template__header header">
        <div class="header__container">
          <a>Home</a>
          <a>Home</a>
          <a>Home</a>
          <a>Home</a>
          <a>Home</a>
        </div>
        <div class="header__line" />
      </div>
      <div class="template__content">
        <nuxt />
      </div>
      <div class="template__footer">
        Footer
      </div>
    </div>
    <base-modal-container />
    <loader-screen />
  </div>
</template>
<script>
export default {
  mounted() {
    // fake loader
    // this.SetLoader(true);
    // setTimeout(() => {
    //   this.SetLoader(false);
    // }, 1000);
  },
};
</script>
<style lang="scss" scoped>
.primary {
  height: 100vh;
  overflow-y: auto;
  &__template {
    height: 100%;
    display: grid;
    grid-template-rows: 100px 1fr auto;
  }
}

.template {
  height: 100%;
  min-height: 100vh;
  overflow: auto;
  &__header {
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
  }
  &__content {
    display: flex;
    flex-direction: column;
    align-items: center;
    position: relative;
  }
}

.header {
  &__container {
    @include container;
    display: flex;
    justify-content: space-between;
    a {
      font-family: 'Gilroy-Bold';
      font-size: 18px;
      line-height: 22px;
      color: #828282;
      cursor: pointer;
    }
    a:hover {
      color: #070707;
    }
  }
  &__line {
    @include container;
    height: 1px;
    margin-top: 25px;
    background-color: #828282;
  }
}
</style>
