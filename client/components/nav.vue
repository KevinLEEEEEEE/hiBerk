<template>
  <div class="main">
    <div :class="[!isOpen ? '' : 'none', 'bar']">
      <div class="btnOpen"  @click="show"></div>
      <ul class="navUlPC">
        <li>Music</li>
        <li>Image</li>
        <li>Image</li>
        <li>Image</li>
        <li>Image</li>
        <li>Image</li>
        <li>Image</li>
      </ul>
    </div>
    <div :class="[isOpen ? '' : 'none', 'content']" @touchmove.prevent>
      <div class="btnClose" @click="hide"></div>
      <ul class="navUlM" >
        <li>Music</li>
        <li>Image</li>
        <li>Image</li>
        <li>Image</li>
        <li>Image</li>
        <li>Image</li>
        <li>Image</li>
      </ul>
    </div>
  </div>

</template>

<script>
export default {
  name: 'myNav',
  data() {
    return {
      isOpen: false,
    };
  },
  methods: {
    show() {
      this.isOpen = true;
    },
    hide() {
      this.isOpen = false;
    },
  },
};
</script>

<style scoped>
  .main {
    position: fixed;
    width: 100%;
    z-index: 1000;
  }
  @media screen and (min-width: 750px){
    .main {
        position: absolute;
        height: 0;
        z-index: 1000;
    }
  }
  .bar {
    display: flex;
    align-items: center;
    height: 40px;
    background: rgba(0, 0, 0, .5);
  }
  @media screen and (min-width: 750px){
    .bar {
        height: 60px;
        background: rgba(0, 0, 0, .2);
    }
  }
  .btnOpen {
    width: 18px;
    height: 12px;
    margin-left: 20px;
    background: linear-gradient(to bottom, white, 0%, white, 20%,
                transparent 20%, transparent 40%, white 40%, white, 60%,
                transparent 60%, transparent 80%, white 80%, white 100%) no-repeat center;
    background-size: 100% 80%;
    cursor: pointer;
  }
  @media screen and (min-width: 750px){
    .btnOpen {
      display: none;
    }
  }
  .content {
    position: absolute;
    top: 0;
    height: 100vh;
    left: 0;
    right: 0;
    z-index: 0;
    color: white;
    background: rgba(0, 0, 0, .9);
  }
  .btnClose {
    width: 40px;
    height: 40px;
    margin-left: 9px;
    outline: 13px solid #fff;
    outline-offset: -32px;
    transform: rotate(45deg);
    cursor: pointer;
  }
  .navUlM {
    padding: 0 10% 0 10%;
    list-style: none;
    font-size: .7rem;
    color: white;
  }
  .navUlM li {
    margin-top: 15px;
    padding-bottom: 5px;
    border-bottom: 1px solid rgba(255, 255, 255, .3);
  }
  .navUlPC {
    display: none;
    flex-direction: row;
    height: 100%;
    margin: 0;
    padding: 0;
    list-style: none;
    font-size: .7rem;
    color: white;
  }
  @media screen and (min-width: 750px){
    .navUlPC {
      display: flex;
    }
  }
  .navUlPC li {
    display: flex;
    align-items: center;
    justify-content: center;
    width: 120px;
    height: 100%;
    }
  .navUlPC li:hover {
    background: rgba(0, 0, 0, .2);
  }
  .none {
    display: none;
  }
</style>

