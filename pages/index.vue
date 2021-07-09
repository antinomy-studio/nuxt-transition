<template>
  <div></div>
</template>

<script>
const getPage = (vm, route) => {
  vm.$children.forEach((el) => console.log(el._name, el))
  return vm.$children.find(child => child.$route.name === route)
}

export default {
  transition: {
    mode: '',
    enter: function (el, done) {
      const page = getPage(this, 'index')
      console.log('enter', this._uid, page._uid)
      done()
    }
  },
  mounted() {
    console.log('mounted', this._uid)
  }
}
</script>
