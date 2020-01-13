<template>
  <div class="container">
    <div class="row">
      <div class="col-xs-12 col-sm-8 col-sm-offset-2 col-md-6 col-md-offset-3">
        <h1
          :class="color"
          v-myOn:mouseover="mouseEnter"
          v-myOn:mouseleave="mouseLeave">Directives Exercise</h1>
        <!-- Exercise -->
        <!-- Build a Custom Directive which works like v-on (Listen for Events) -->

      </div>
    </div>
  </div>
</template>

<script>


export default {
  name: 'app',
  components: {

  },
  directives: {
    'myOn': {
      bind(el, binding) {
        let type = binding.arg
        let fn = binding.value

        el.addEventListener(type, fn)
      }
    }
  },
  methods: {
    mouseEnter() {
      this.color = 'red'
      // eslint-disable-next-line no-console
      console.log('Mouse entered!');
    },
    mouseLeave() {
      this.color = 'blue'
      // eslint-disable-next-line no-console
      console.log('Mouse leaved!');
    }
  },
  data: function () {
    return {color: ''}
  }
}
</script>

<style>
  .red {
    color: red;
  }
  .blue {
    color: blue;
  }
</style>
