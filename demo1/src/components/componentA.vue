<template>
    <div class="hello">
      <h1>{{ msg }}</h1>
      <h2>{{msgfromfather}}</h2>
      <button v-on:click="onClickMe">Click!</button>
    </div>
</template>
<script>
export default {
  data: function () {
    return {
      msg: 'hello from component a!'
    }
  },
  props: ['msgfromfather'],
  events: {
    'onAddnew': function (items) {
      console.log(items)
    }
  },
  methods: {
    onClickMe: function () {
//      console.log(this.msgfromfather)
      this.$emit('child-tell-me-something', this.msg)
    }
  }
}
</script>
