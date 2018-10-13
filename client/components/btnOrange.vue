<template>
  <div class="btn" @click.prevent="click">
    {{ text }}
  </div>
</template>

<script>

export default {
  name: 'btn_red',
  props: {
    text: {
      type: String,
      default: 'button',
    },
  },
  methods: {
    click() {
      console.log('child click');
      this.$emit('click', {
        text: this.text,
      });
    },
  },
};
</script>

<style scoped>
@import '../assets/css/global.css';

.btn {
  border: 1.5px solid rgba(255, 168, 30, 1.0);
  background: rgba(0, 0, 0, .3);
  color: rgba(255, 168, 30, 1.0);
}
@media screen and (min-width: 750px){
  .btn {
    width: 12rem;
    height: 2.7rem;
    font-size: .8rem;
  }
  .btn:hover {
    background: rgba(255, 168, 30, .05);
  }
}
</style>
