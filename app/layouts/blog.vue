<template>
  <div class="blog-root">
    <div class="main-wrap">
      <main-header />
      <v-container :class="{ fixed: isDesktop }">
        <Nuxt />
      </v-container>
    </div>
    <section id="footer">
      <footer-with-deco />
    </section>
  </div>
</template>


<style scoped lang="scss">
@import '~/assets/styles';

.blog-root {
  background: linear-gradient(
    -45deg,
    $palette-primary-main 20%,
    $palette-primary-dark 70%
  );
  position: relative;
  padding: spacing(25, 0, 15);
  @include breakpoints-up(lg) {
    height: 200px;
    padding: spacing(30, 0, 5);
  }
  @include breakpoints-down(xs) {
    padding: spacing(25, 0, 10);
    position: relative;
  }
}

.main-wrap {
  position: relative;
  width: 100%;
  overflow: hidden;
  @include palette-text-primary;
  .theme--dark & {
    background-color: $dark-background-default;
  }
  .theme--light & {
    background-color: $light-background-paper;
  }
}

.decoration {
  position: absolute;
  width: 100%;
  height: 100%;
  top: 0;
  @include left(0);
  overflow: hidden;
  clip: rect(0, auto, auto, 0);
  svg {
    fill: $palette-secondary-main;
    opacity: 0.15;
    position: fixed;
    top: 0;
  }
}

.left-deco {
  left: 0;
  right: auto;
  width: 1200px;
  height: 1500px;
  transform: scale(0.8);
  transform-origin: top left;
}

.right-deco {
  left: auto;
  right: 0;
  height: 1500px;
  transform: scale(0.5);
  transform-origin: top right;
}

@function section-margin($margin) {
  @return $margin * 20;
}
.main-wrap {
  position: relative;
  width: 100%;
  overflow: hidden;
  @include palette-text-primary;
  .theme--dark & {
    background-color: $dark-background-default;
  }
  .theme--light & {
    background-color: $light-background-paper;
  }
}
.space-bottom {
  margin-bottom: section-margin($spacing1);
  @include breakpoints-down(sm) {
    margin-bottom: section-margin(6px);
  }
}
.space-bottom-testi {
  @include breakpoints-up(md) {
    margin-bottom: section-margin($spacing1);
  }
}
.space-bottom-short {
  margin-bottom: section-margin($spacing1 / 2);
}
.space-top {
  margin-top: section-margin($spacing1);
  @include breakpoints-down(sm) {
    margin-top: section-margin(6px);
  }
}
.space-top-short {
  margin-top: section-margin($spacing1 / 2);
}
.container-wrap {
  margin-top: -40px;
  > section {
    position: relative;
  }
}
</style>

<script>
import Header from '~/components/Header'
import FooterWithDeco from '~/components/Footer/FooterWithDeco'

import brand from '~/static/text/brand'

export default {
  layout: 'blog',
  components: {
    'main-header': Header,
    FooterWithDeco,
  },
  computed: {
    isTablet() {
      return this.$mq === 'mdDown' || this.$mq === 'smDown' || this.$mq === 'xsDown' // eslint-disable-line
    },
    isMobile() {
      return this.$mq === 'smDown' || this.$mq === 'xsDown'
    },
  },
  head() {
    return {
      title: brand.lotus.name + ' - Home Page',
    }
  },
}
</script>
