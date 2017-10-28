# 微信小程序 wepyjs NavBar组件
![NavBar](https://raw.githubusercontent.com/chenyangcun/images/master/navbar/navbar.jpg)

## 说明
基于wepy框架开发微信小程序NavBar控件


## 使用

### 安装组件
```
npm install wepy-com-navbar --save
```

### 使用例子
```
<template>
  <navBar :tabs="tabs" :currentTab.sync="currentTab"></navBar>
  <swiper current="{{currentTab}}"  duration="300"
          bindchange="bindChange">
    <swiper-item>
      <view>TAB1</view>
    </swiper-item>
    <swiper-item>
      <view>TAB2</view>
    </swiper-item>
    <swiper-item>
      <view>TAB3</view>
    </swiper-item>
  </swiper>

</template>
<script>
  import wepy from 'wepy'
  import NavBar from 'wepy-com-navbar'

  export default class Index extends wepy.page {
    config = {
      navigationBarTitleText: 'NavBar测试',
      enablePullDownRefresh: false
    }

    data = {
      currentTab: 0,
      tabs: ['TAB1', 'TAB2', 'TAB3']
    }
    methods = {
      bindChange(e) {
        this.currentTab = e.detail.current
      }
    }

    components = {
      navBar: NavBar
    }
  }
</script>
```


