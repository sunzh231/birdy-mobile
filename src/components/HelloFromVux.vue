<template>
  <div>
    <swiper loop auto :list="demo06_list" :index="demo06_index" @on-index-change="demo06_onIndexChange"></swiper>
    <group>
      <x-input title="姓名" placeholder="请输入您的职业" v-model="name"></x-input>
    </group>
    <group>
      <x-input title="手机号码" name="mobile" placeholder="请输入手机号码" keyboard="number" is-type="china-mobile"></x-input>
    </group>
    <group>
      <selector title="贷款金额" placeholder="请选择贷款金额" :options="loanAmountOptions" v-model="value"></selector>
    </group>
    <group>
      <x-input title="职业" placeholder="请输入您的职业" v-model="value"></x-input>
    </group>
    <group>
      <selector title="家庭年收入" placeholder="请选择家庭年收入" :options="loanAmountOptions" v-model="value"></selector>
    </group>
    <box gap="10px 10px">
      <x-button type="primary">提交微信贷款申请</x-button>
    </box>
  </div>
</template>

<script>
import { Swiper, GroupTitle, SwiperItem, XButton, Divider, Group, XInput, Selector, Box } from 'vux'
const baseList = [{
  url: 'javascript:',
  img: 'https://static.vux.li/demo/1.jpg',
  title: '送你一朵fua'
}, {
  url: 'javascript:',
  img: 'https://static.vux.li/demo/2.jpg',
  title: '送你一辆车'
}, {
  url: 'javascript:',
  img: 'https://static.vux.li/demo/3.jpg',
  title: '送你一次旅行'
}]

const urlList = baseList.map((item, index) => ({
  url: 'http://m.baidu.com',
  img: item.img,
  title: `(可点击)${item.title}`
}))

export default {
  components: {
    Swiper,
    SwiperItem,
    GroupTitle,
    XButton,
    Divider,
    Group,
    XInput,
    Selector,
    Box
  },
  ready () {
  },
  methods: {
    demo06_onIndexChange (index) {
      this.demo06_index = index
    }
  },
  data () {
    return {
      demo06_list: urlList,
      demo06_index: 0,
      name: '',
      value: '',
      loanAmountOptions: [
        { key: 1, value: '1万'},
        { key: 1, value: '1万'},
        { key: 1, value: '1万'},
        { key: 1, value: '1万'},
        { key: 1, value: '1万'},
        { key: 1, value: '1万'},
        { key: 1, value: '1万'},
        { key: 1, value: '1万'},
        { key: 1, value: '1万'},
        { key: 1, value: '1万'},
        { key: 1, value: '1万'},
        { key: 1, value: '1万'},
        { key: 1, value: '1万'}
      ]
    }
  }
}
</script>

<style scoped>
.copyright {
  font-size: 12px;
  color: #ccc;
  text-align: center;
}
.text-scroll {
  border: 1px solid #ddd;
  border-left: none;
  border-right: none;
}
.text-scroll p{
  font-size: 12px;
  text-align: center;
  line-height: 30px;
}
.black {
  background-color: #000;
}
.title{
  line-height: 100px;
  text-align: center;
  color: #fff;
}
.animated {
  animation-duration: 1s;
  animation-fill-mode: both;
}
.vux-indicator.custom-bottom {
  bottom: 30px;
}
@-webkit-keyframes fadeInUp {
  from {
    opacity: 0;
    transform: translate3d(0, 100%, 0);
  }
  100% {
    opacity: 1;
    transform: none;
  }
}
@keyframes fadeInUp {
  from {
    opacity: 0;
    transform: translate3d(0, 100%, 0);
  }
  100% {
    opacity: 1;
    transform: none;
  }
}
.fadeInUp {
  animation-name: fadeInUp;
}
.swiper-demo-img img {
  width: 100%;
}
</style>
