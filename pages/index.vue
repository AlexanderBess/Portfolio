<template>
  <div class="example">
    <div class="example__content">
      <div class="example__title">
        Title
      </div>
    </div>
  </div>
</template>
<script>
export default {

};
</script>

<style lang="scss" scoped>
.example {
  @include container;
  background: #dbdfe3;
  &__content {
    height: 300px;
  }
  &__title {
    font-size: 60px;
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
