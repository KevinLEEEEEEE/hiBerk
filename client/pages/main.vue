<template>
  <div id="main">
    <myNav></myNav>
    <bannerL
      v-for="(banner, index) in bannerL"
      :key="index"
      :title="banner.title"
      :des="banner.des">
    </bannerL>
    <div class="bannerM">
      <bannerM
        v-for="(banner, index) in bannerM"
        :key="index"
        :title="banner.title"
        :des="banner.des"
        :bg="banner.bg">
      </bannerM>
    </div>
    <div class="bannerS">
      <bannerS
        v-for="(banner, index) in bannerS"
        :key="index"
        :self="index"
        :total="bannerS.length"
        :title="banner.title"
        :des="banner.des"
        :fullDes="banner.fullDes"
        :bg="banner.bg">
      </bannerS>
    </div>
    <myFooter></myFooter>
  </div>
</template>

<script>
import myNav from '../components/nav';
import bannerL from '../components/bannerL';
import bannerM from '../components/bannerM';
import bannerS from '../components/bannerS';
import myFooter from '../components/myFooter';

export default {
  name: 'mainPage',
  data() {
    return {
      bannerL: [
        {
          title: '嘿！旋律',
          des: '聆听聆听聆听聆听聆听聆听聆听聆听聆听聆听聆聆听聆听聆听聆听聆听',
        },
      ],
      bannerM: [
        {
          title: '嘿！旋律',
          des: '聆听聆听聆听聆听聆听聆听聆听聆听聆听聆听聆聆听聆听聆听聆听聆听',
          bg: 'bg_M_1.jpg',
        },
        {
          title: '嘿！旋律',
          des: '聆听聆听聆听聆听聆听聆听聆听聆听聆听聆听聆聆听聆听聆听聆听聆听',
          bg: 'bg_M_2.jpg',
        },
        {
          title: '嘿！旋律',
          des: '聆听聆听聆听聆听聆听聆听聆听聆听聆听聆听聆聆听聆听聆听聆听聆听',
          bg: 'bg_M_3.jpg',
        },
      ],
      bannerS: [
        {
          title: '嘿！旋律',
          des: '聆听聆听聆听聆听聆听聆听聆听聆听聆听聆听聆聆听聆听聆听聆听聆听',
          fullDes: ['聆听聆听聆听聆听聆听聆听聆听聆听聆听聆听聆聆听聆听聆听聆听聆',
            '听聆听聆听聆听聆听聆听聆听聆听聆听聆听聆听聆聆听聆听聆听聆听聆听',
            '听聆听聆听聆听聆听聆听聆听聆听聆听聆听聆听聆聆听聆听聆听聆听聆听',
            '听聆听聆听聆听聆听聆听聆听聆听聆听聆听聆听聆聆听聆听聆听聆听聆听',
            '听聆听聆听聆听聆听聆听聆听聆听聆听聆听聆听聆聆听聆听聆听聆听聆听',
            '听聆听聆听聆听聆听聆听聆听聆听聆听聆听聆听聆聆听聆听聆听聆听聆听',
            '听聆听聆听聆听聆听聆听聆听聆听聆听聆听聆听聆聆听聆听聆听聆听聆听'],
          bg: 'bg_S_1.jpg',
        },
        {
          title: '嘿！旋律',
          des: '聆听聆听聆听聆听聆听聆听聆听聆听聆听聆听聆聆听聆听聆听聆听聆听',
          fullDes: ['聆听聆听聆听聆听聆听聆听聆听聆听聆听聆听聆聆听聆听聆听聆听聆',
            '听聆听聆听聆听聆听聆听聆听聆听聆听聆听聆听聆聆听聆听聆听聆听聆听'],
          bg: 'bg_S_2.jpg',
        },
        {
          title: '嘿！旋律',
          des: '聆听聆听聆听聆听聆听聆听聆听聆听聆听聆听聆聆听聆听聆听聆听聆听',
          fullDes: ['聆听聆听聆听聆听聆听聆听聆听聆听聆听聆听聆聆听聆听聆听聆听聆',
            '听聆听聆听聆听聆听聆听聆听聆听聆听聆听聆听聆聆听聆听聆听聆听聆听'],
          bg: 'bg_S_3.jpg',
        },
        {
          title: '嘿！旋律',
          des: '聆听聆听聆听聆听聆听聆听聆听聆听聆听聆听聆聆听聆听聆听聆听聆听',
          fullDes: ['聆听聆听聆听聆听聆听聆听聆听聆听聆听聆听聆聆听聆听聆听聆听聆',
            '听聆听聆听聆听聆听聆听聆听聆听聆听聆听聆听聆聆听聆听聆听聆听聆听'],
          bg: 'bg_S_4.jpg',
        },
        {
          title: '嘿！旋律',
          des: '聆听聆听聆听聆听聆听聆听聆听聆听聆听聆听聆聆听聆听聆听聆听聆听',
          fullDes: ['聆听聆听聆听聆听聆听聆听聆听聆听聆听聆听聆聆听聆听聆听聆听聆',
            '听聆听聆听聆听聆听聆听聆听聆听聆听聆听聆听聆聆听聆听聆听聆听聆听'],
          bg: 'bg_S_4.jpg',
        },
        {
          title: '嘿！旋律',
          des: '聆听聆听聆听聆听聆听聆听聆听聆听聆听聆听聆聆听聆听聆听聆听聆听',
          fullDes: ['聆听聆听聆听聆听聆听聆听聆听聆听聆听聆听聆聆听聆听聆听聆听聆',
            '听聆听聆听聆听聆听聆听聆听聆听聆听聆听聆听聆聆听聆听聆听聆听聆听'],
          bg: 'bg_S_1.jpg',
        },
        {
          title: '嘿！旋律',
          des: '聆听聆听聆听聆听聆听聆听聆听聆听聆听聆听聆聆听聆听聆听聆听聆听',
          fullDes: ['聆听聆听聆听聆听聆听聆听聆听聆听聆听聆听聆聆听聆听聆听聆听聆',
            '听聆听聆听聆听聆听聆听聆听聆听聆听聆听聆听聆聆听聆听聆听聆听聆听'],
          bg: 'bg_S_2.jpg',
        },
        {
          title: '嘿！旋律',
          des: '聆听聆听聆听聆听聆听聆听聆听聆听聆听聆听聆聆听聆听聆听聆听聆听',
          fullDes: ['聆听聆听聆听聆听聆听聆听聆听聆听聆听聆听聆聆听聆听聆听聆听聆',
            '听聆听聆听聆听聆听聆听聆听聆听聆听聆听聆听聆聆听聆听聆听聆听聆听'],
          bg: 'bg_S_3.jpg',
        },
      ],
    };
  },
  methods: {
  },
  components: {
    myNav,
    bannerL,
    bannerM,
    bannerS,
    myFooter,
  },
};
</script>

<style>
@import '../assets/css/global.css';
#main {
  display: flex;
  flex-direction: column;
  align-items: center;
  position: relative;
  min-width: 100px;
}
.bannerS {
  padding: 0 10%;
}
</style>
