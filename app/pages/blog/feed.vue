<template>
  <div class="main-wrap">
    <div class="page-wrap pt-16">


      <!-- :caption="$t('lotusLanding.features.title')" -->
      <!-- <title-main
        caption="Our Articles"
        align="center"
        class='use-text-title pt-12'
        color="primary"
      >
      </title-main> -->
      <Blog />
    </div>
  </div>
</template>

<script>
import Blog from '~/components/Blog/Blog.vue'

export default {
  layout: 'blog',
  components: {
    Blog,
  },
  computed: {
    isTablet() {
      return this.$mq === 'mdDown' || this.$mq === 'smDown' || this.$mq === 'xsDown' // eslint-disable-line
    },
    isMobile() {
      return this.$mq === 'smDown' || this.$mq === 'xsDown'
    },
    isDesktop() {
      const lgUp = this.$store.state.breakpoints.lgUp
      return lgUp.indexOf(this.$mq) > -1
    },
  },
  head() {
    return {
      title: 'Lotus' + ' - Home Page',
    }
  },
}
</script>
