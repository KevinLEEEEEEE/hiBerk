<template>
  <div class="banner" :style="bgImg">
    <div class="bannerContent">
        <div id="textBox">
        <p id="title">{{ title }}</p>
        <p id="description">{{ des }}</p>
        </div>
        <div id="btnBox">
        <btnOrange text="预览效果" @click="click" class="btn"></btnOrange>
        </div>
    </div>
  </div>
</template>

<script>
import btnRed from './btnRed';
import btnOrange from './btnOrange';

export default {
  name: 'bannerM',
  props: {
    title: {
      type: String,
      default: 'no title',
    },
    des: {
      type: String,
      default: 'no des',
    },
    bg: {
      type: String,
      default: 'bg_M_default.jpg',
    },
  },
  data() {
    return {
      bgImg: {
        background: `url(./static/img/${this.bg})`,
      },
    };
  },
  methods: {
    click(message) {
      console.log(`father click  ${message.text}`);
    },
  },
  components: {
    btnRed,
    btnOrange,
  },
};
</script>

<style scoped>
.banner {
  display: flex;
  flex-direction: column;
  justify-content: flex-end;
  width: 100vw;
  height: 100vw;
  background-size: cover;
}
@media screen and (min-width: 750px){
  .banner {
    height: 750px;
    justify-content: center;
    align-items: flex-end;
    background-size: cover;
  }
}
.bannerContent {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    width: 100%;
    height: 100%;
    padding: 60% 0 0 0;
    background: linear-gradient(transparent 60%, rgba(0, 0, 0, .5) 60%);
}
@media screen and (min-width: 750px){
  .bannerContent {
    align-items: flex-end;
    padding: 0 10% 0 0;
    background: linear-gradient(to right, transparent 50%, rgba(0, 0, 0, .7) 90%);
  }
}
#textBox {
  display: flex;
  flex-direction: column;
  justify-content: center;
  color: white;
  text-align: center;
}
@media screen and (min-width: 750px){
  #textBox {
    align-items: flex-end;
  }
}
#title {
  margin: 0;
  font-size: 1.4rem;
  font-weight: bold;
}
@media screen and (min-width: 750px){
  #title {
    font-size: 2.5rem;
  }
}
#description {
  font-size: .65rem;
  padding: 0 10%;
}
@media screen and (min-width: 750px){
  #description {
    width: 350px;
    padding: 0;
    font-size: .9rem;
    letter-spacing: .1em;
    text-align: end;
  }
}
#btnBox {
  display: flex;
  flex-direction: column;
  justify-content: center;
}
@media screen and (min-width: 750px){
  #btnBox {
    margin-top: 20px;
  }
}
.btn {
  margin: 5px;
}
</style>
