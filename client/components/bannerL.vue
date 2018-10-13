<template>
  <div class="banner">
    <div id="textBox">
      <p id="title">{{ title }}</p>
      <p id="description">{{ des }}</p>
    </div>
    <div id="btnBox">
      <btnRed text="立即下载" @click="click" class="btn"></btnRed>
      <btnOrange text="预览效果" @click="click" class="btn"></btnOrange>
    </div>
  </div>
</template>

<script>
import btnRed from './btnRed';
import btnOrange from './btnOrange';

export default {
  name: 'bannerL',
  props: {
    title: {
      type: String,
      default: 'no title',
    },
    des: {
      type: String,
      default: 'no des',
    },
  },
  data() {
    return {

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
  align-items: center;
  width: 100%;
  height: 600px;
  background: url('../assets/bg_L_1s.jpg');
  background-size: cover;
}
@media screen and (min-width: 750px){
  .banner {
    height: 1080px;
    justify-content: center;
    align-items: flex-start;
    background: url('../assets/bg_L_1.jpg');
    background-size: cover;
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
    align-items: flex-start;
    margin-left: 10%;
  }
}
#title {
  margin: 0;
  font-size: 2rem;
  font-weight: bold;
}
@media screen and (min-width: 750px){
  #title {
    font-size: 3.5rem;
  }
}
#description {
  font-size: .8rem;
  padding: 0 10%;
}
@media screen and (min-width: 750px){
  #description {
    width: 350px;
    padding: 0;
    font-size: .9rem;
    letter-spacing: .1em;
    text-align: start;
  }
}
#btnBox {
  display: flex;
  flex-direction: column;
  justify-content: center;
  margin: 10px 0 50px 0;
}
@media screen and (min-width: 750px){
  #btnBox {
    margin-left: 10%;
  }
}
.btn {
  margin: 10px;
}
</style>
