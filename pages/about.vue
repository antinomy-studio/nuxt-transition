<template>
  <div class="About">
    <NuxtLink to="/">Index</NuxtLink>
  </div>
</template>

<script>
const getPage = (vm, route) => {
  console.group('this.$children')
  vm.$children.forEach((el) => console.log(el._uid, el.$el))
  console.groupEnd()
  return vm.$children.find(child => child.$route.name === route)
}

export default {
  transition: {
    mode: '',
    enter: function (el, done) {
      const page = getPage(this, 'about')
      console.log('about:enter', this._uid, page._uid)
      done()
    },
    leave: function (el, done) {
      const page = getPage(this, 'about')
      console.log('about:leave', this._uid, page)
      done()
    },
  },
  mounted() {
    console.log('mounted', this._uid)
  }
}
</script>