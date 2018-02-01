# wepy-swipe-delete (废弃)

> 微信小程序框架wepy - 滑动删除插件, 支持自定义内容区


![](http://o80ronwlu.bkt.clouddn.com/wepy-swipe-del.gif)

[![npm version](https://img.shields.io/npm/v/wepy-swipe-delete.svg)](https://www.npmjs.com/package/wepy-swipe-delete)

## Requirements
- wepy: "^1.5.2"

## Usage
#### install

``` sh
 npm install wepy-swipe-delete --save
```

#### 父组件 parents.wepy

```vue
<template>
  <repeat for="{{list}}" key="index" index="index" item="item">
    <swipeDelete :swipeData="item" @delItem.user="handleDelItem">
      <view class="swipe-title">
        {{item.title}}
      </view>
    </swipeDelete>
  </repeat>
</template>

<script>
  import wepy from 'wepy'
  import swipeDelete from 'wepy-swipe-delete'

  export default class Index extends wepy.page {
    components = {
      swipeDelete
    }

    data = {
      list: [
        {id: 1, title: '标题1', style: 0},
        {id: 2, title: '标题2', style: 0}
      ]
    }

    methods = {
      handleDelItem (itemData) {
        console.log(itemData)
      }
    }
  }
</script>
```
