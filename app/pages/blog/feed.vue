<template>
  <div class="main-wrap">
    <main-header/>
    <Calculator
    />
  </div>
</template>

<script>
import Calculator from '~/components/Forms/Calculator'

export default {
  loading: false,
  layout: 'blog',
  components: {
    Calculator,
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
