<template>
  <section class="hero">
    <div class="hero__contentWrapper">
      <p class="hero__heading">Learning from My Parents!</p>
      <h1 class="hero__extraLead">
        Un evento organizado para exponer las empresas y/o emprendimientos de los padres de familia
        de nuestra institución.
      </h1>
    </div>
    <!-- <g-link class="blogCard__arrow" :to="edge.node.path">
              <font-awesome :icon="['fas', 'arrow-right']" />
            </g-link> -->
    <div class="hero__scrollBtn">
      <g-link class="blogCard__arrow" to="/blog">
        <font-awesome :icon="['fas', 'arrow-right']" />
      </g-link>
    </div>
  </section>
</template>

<script>
import SocialIcons from "@/components/SocialIcons.vue"

export default {
  components: {
    SocialIcons
  }
}
</script>

<style lang="scss" scoped>
.hero {
  position: relative;
  display: grid;
  overflow: hidden;
  height: 100vh;
  grid-template-columns: 1fr 60px 1fr;
  grid-template-rows: 2fr 1fr 1fr;
  grid-template-areas:
    ". . ."
    "contentWrapper contentWrapper contentWrapper"
    "socialIcons scrollBtn .";
  @media (min-width: $breakpoint-lg) {
    grid-template-columns: 1fr 4fr 60px 5fr;
    grid-template-rows: 1fr 1fr 1fr;
    grid-template-areas:
      ". . . ."
      ". contentWrapper contentWrapper contentWrapper"
      "socialIcons . scrollBtn .";
  }

  &__contentWrapper {
    position: relative;
    grid-area: contentWrapper;
    align-self: center;
    margin-left: 1rem;
    &:before {
      position: absolute;
      z-index: $layer-negative-z-index;
      top: 50%;
      left: 10px;
      font-size: 250px;
      content: "JSN";
      color: $color-text-alt;
      transition: color $duration-animation-base ease;
      transform: translateY(-50%);
      @media (min-width: $breakpoint-lg) {
        font-size: 360px;
      }
    }
    &:hover:before {
      color: rgba($color-secondary, 0.3);
    }
  }

  &__heading {
    @extend %typography-xxlarge;
    margin: 0 0 0 -0.07em;
    font-size: 3.2rem;
  }
  &__extraLead {
    @extend %typography-small;
    margin-top: 0;
  }

  &__socialIcons {
    grid-area: socialIcons;
    align-self: end;
    margin-bottom: 13vh;
    display: flex;
    justify-content: flex-start;
    @media (min-width: $breakpoint-lg) {
      display: flex;
      flex-direction: column;
      align-items: flex-start;
    }
  }

  &__scrollBtn {
    grid-area: scrollBtn;
    justify-self: center;
    align-self: end;
    margin-bottom: 13vh;
  }
}
</style>
