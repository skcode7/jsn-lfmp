<template>
  <footer class="footer">
    <div class="footer__inner container">
      <!-- <LogoComponent class="footer__logo" version="fullWhite" desc="Footer Logo" /> -->

      <p class="footer__copyright">
        &copy; {{ thisYear }}.
        <!-- <g-link to="/">HOME_PAGE_NAME</g-link> -->
        Created by
        <a href="https://carlosencalada.dev" target="_blank" rel="noopener noreferrer">
          Carlos Encalada
        </a>
        <br />
        Powered by
        <a href="https://jsncaritasalegres.com" target="_blank" rel="noopener noreferrer">
          Caritas Alegres
        </a>
      </p>
    </div>
  </footer>
</template>

<script>
import LogoComponent from "@/components/LogoComponent.vue"
import SocialIcons from "@/components/SocialIcons.vue"

export default {
  components: {
    LogoComponent,
    SocialIcons
  },
  data() {
    return {
      thisYear: new Date().getFullYear()
    }
  }
}
</script>

<style lang="scss" scoped>
.footer {
  @extend %skewBorderBeforeFlip;
  padding-top: 25px;
  display: flex;
  justify-content: center;
  color: $color-text-alt2;
  background-color: $color-body-bg-alt;

  &__logo {
    margin: 0 auto 17px;
    display: block;
    width: 160px;
  }

  &__copyright {
    text-align: center;

    a {
      color: $color-text-alt2;
      &:hover {
        color: $color-primary;
      }
    }
  }
}
</style>
