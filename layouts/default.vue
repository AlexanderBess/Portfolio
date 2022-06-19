<template>
  <div class="primary">
    <div class="primary__template template">
      <div class="template__header header">
        <div class="header__container">
          <a
            v-for="(name, key) in titles"
            :id="`ELEMENT_${name}`"
            :ref="`ELEMENT_${name}`"
            :key="key"
            class="header__title"
            :class="name === choosenBlock ? 'header__title_active' : ''"
            @click="chooseBlock(name)"
          >
            {{ name }}
          </a>
        </div>
        <div class="header__line" />
      </div>
      <div class="template__content">
        <nuxt />
      </div>
      <div class="template__footer footer">
        <div class="footer__socials">
          <a
            v-for="(social, key) in socials"
            :key="`social-${key}`"
            class="footer__social"
            :class="`footer__social_${social.name}`"
            :href="social.link"
            target="_blank"
          />
        </div>
        <div class="footer__text">
          Follow me on<br>
          LinkedIn, Telegram, Instagram, GitHub
        </div>
      </div>
    </div>
    <base-modal-container />
    <loader-screen />
  </div>
</template>
<script>
export default {
  data() {
    return {
      choosenBlock: 'Home',
    };
  },
  computed: {
    titles() {
      return [
        this.$t('header.home'),
        this.$t('header.aboutMe'),
        this.$t('header.skills'),
        this.$t('header.portfolios'),
        this.$t('header.contacts'),
      ];
    },
    socials() {
      return [
        {
          name: 'linkedin',
          link: 'https://www.linkedin.com/in/alex-bessmelcev/',
        },
        {
          name: 'telegram',
          link: 'https://t.me/Alex_Sage',
        },
        {
          name: 'instagram',
          link: 'https://www.instagram.com/alexanderbessmelcev/',
        },
        {
          name: 'github',
          link: 'https://github.com/AlexanderBess',
        },
      ];
    },
  },
  mounted() {
    // fake loader
    this.SetLoader(true);
    setTimeout(() => {
      this.SetLoader(false);
    }, 1000);
  },
  methods: {
    chooseBlock(name) {
      this.choosenBlock = name;
    },
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
    grid-template-rows: auto 1fr auto;
  }
}

.template {
  height: 100%;
  min-height: 100vh;
  overflow: auto;
  &__header {
    position: sticky;
    top: 0px;
    z-index: 10;
    padding-top: 20px;

    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;

    -webkit-backdrop-filter: blur(5px);
    backdrop-filter: blur(5px);
    background: #FFFFFFBF;
  }
  &__content {
    display: flex;
    flex-direction: column;
    align-items: center;
    position: relative;
  }
  &__footer {
    display: grid;
    grid-gap: 20px;
    padding-bottom: 10%;
  }
}

.header {
  &__container {
    @include container;
    display: flex;
    justify-content: space-between;
  }
  &__title {
    font-family: 'Gilroy-Bold';
    font-size: 18px;
    line-height: 22px;
    color: #828282;
    cursor: pointer;
    text-decoration: none;
    &_active {
      color: #070707;
    }
  }
  &__title:hover {
    color: #070707;
  }
  &__line {
    @include container;
    height: 1px;
    margin-top: 25px;
    background-color: #828282;
  }
}
.footer {
  &__socials {
    display: grid;
    grid-template-columns: repeat(4, 41px);
    justify-content: center;
    grid-gap: 60px;
  }
  &__social {
    width: 41px;
    height: 41px;
    background-size: contain;
    &_linkedin {
      border-radius: 5px;
      background-image: url('assets/img/social/linkedin.svg');
    }
    &_linkedin:hover {
      background-color: #82828261;
    }
    &_telegram {
      border-radius: 50%;
      background-image: url('assets/img/social/telegram.svg');
    }
    &_telegram:hover {
      background-color: #82828261;
    }
    &_instagram {
      border-radius: 12px;
      background-image: url('assets/img/social/instagram.svg');
    }
    &_instagram:hover {
      background-color: #82828261;
    }
    &_github {
      border-radius: 50%;
      background-image: url('assets/img/social/github.svg');
    }
    &_github:hover {
      background-color: #82828261;
    }
  }
  &__text {
    text-align: center;
    font-family: 'Gilroy-Medium';
    font-size: 14px;
    color: #828282;
  }
}
</style>
