<template>
  <div v-bind:class="[even ? 'bannerEven' : 'bannerOdd', 'banner', 'clear']">
    <div class="content" :style="bgImg">
      <div class="fullDescription">
          <p v-for="(desClip, index) in fullDes" :key="index" class="clear">
              {{ desClip }}
          </p>
      </div>
      <div class="counter">
          <p class="clear cp1">{{ selfIndex }}</p>
          <p class="clear cp2">/</p>
          <p class="clear cp3">{{ totalIndex }}</p>
      </div>
      <div class="bannerContent">
          <div class="textBox">
            <p class="title clear">{{ title }}</p>
            <p class="description clear">{{ des}}</p>
          </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'bannerS',
  props: {
    self: {
      type: Number,
      default: 0,
    },
    total: {
      type: Number,
      default: 0,
    },
    bg: {
      type: String,
      default: 'bg_S_1.jpg',
    },
    title: {
      type: String,
      default: 'no title',
    },
    des: {
      type: String,
      default: 'no des',
    },
    fullDes: {
      type: Array,
      default() {
        return [];
      },
    },
  },
  computed: {
    selfIndex() {
      return `0${parseInt(this.self + 1, 10)}`;
    },
    totalIndex() {
      return `0${parseInt(this.total, 10)}`;
    },
    even() {
      return this.self % 5 < 3;
    },
  },
  data() {
    return {
      bgImg: {
        backgroundImage: `url(./static/img/${this.bg})`,
      },
    };
  },
  methods: {
    click(message) {
      console.log(`father click  ${message.text}`);
    },
  },
};
</script>

<style scoped>
.banner {
    display: flex;
    justify-content: center;
    float: left;
    padding-top: 20px;
}
@media screen and (min-width: 750px){
    .banner {
        padding: 2px;
    }
    .bannerEven {
        width: calc((100% - 12px) / 3);
        height: 16vw;
    }
    .bannerOdd {
        width: calc((100% - 8px) / 2);
        height: 23vw;
    }
}
.content {
    display: flex;
    flex-direction: column;
    justify-content: space-between;
    position: relative;
    width: 75vw;
    height: 75vw;
    background-size: cover;
}
@media screen and (min-width: 750px){
  .content {
      width: 100%;
      height: 0;
  }
}
.content:hover .fullDescription {
    display: block;
}
.content:hover .bannerContent {
    display: none;
}
.content:hover .counter {
    display: none;
}
.content:hover::before {
    content: '';
    width: 100%;
    height: 100%;
    background: linear-gradient(black 0%, transparent 25%, transparent 75%, black 100%);
    pointer-events: none;
    z-index: 3;
}
@media screen and (min-width: 750px){
    .content {
        justify-content: flex-end;
        width: 100%;
        height: 100%;
    }
}
.fullDescription {
    display: none;
    position: absolute;
    top: 0;
    bottom: 0;
    left: 0;
    right: 0;
    padding: 15%;
    overflow: scroll;
    background: rgba(0, 0, 0, .8);
}
@media screen and (min-width: 750px){
    .fullDescription {
        padding: 10% 15%;
    }
}
.fullDescription::-webkit-scrollbar{
    display:none;
}
.fullDescription p{
    margin-top: 3%;
    font-size: .8rem;
    text-indent: 2rem;
    color: white;
}
.counter {
    position: relative;
    color: white;
}
@media screen and (min-width: 750px){
    .counter {
        display: none;
    }
}
.cp1 {
    position: absolute;
    top: 0;
    right: 35px;
    font-size: 2rem;
}
.cp2 {
    position: absolute;
    top: 15px;
    right: 25px;
    font-size: 1.5rem;
}
.cp3 {
    position: absolute;
    top: 30px;
    right: 9px;
    font-size: 1rem;
}
.bannerContent {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    padding: 0 0 8% 5%;
}
@media screen and (min-width: 750px){
    .bannerContent {
        align-items: flex-start;
        padding: 0 0 5% 5%;
        transition: all .2s ease;
    }
}
.textBox {
    display: flex;
    flex-direction: column;
    justify-content: flex-start;
    width: 100%;
    color: white;
}
.title {
    font-size: 1.3rem;
}
@media screen and (min-width: 750px){
    .title {
        font-size: 1.5rem;
    }
}
.description {
    padding: 0 25% 0 0;
    text-decoration: underline;
    font-size: .7rem;
}
@media screen and (min-width: 750px){
    .description {
        width: calc(100% - 200px);
        min-width: 200px;
        padding: 0;
        font-size: .6rem;
        letter-spacing: .1em;
        text-align: start;
    }
}
.clear {
    margin: 0;
}
</style>
