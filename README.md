# notice-puge

![default](http://p5qgrn52w.bkt.clouddn.com/%E5%BD%95%E5%88%B6_2018_07_02_18_24_37_54.gif)

安装
```
npm i -save notice-puge
或
yarn add notice-puge
```

使用
```
<template lang="pug">
  <div>
    <Notice v-model="notice"></Notice>
  </div>
</template>

<script>
import Notice from 'notice-puge'
export default {
  name: 'home',
  components: {
    Notice
  },
  data () {
    return {
      notice: "XX系统于2018-10-12故障，已下发短信提醒。",
    }
  }
}
</script>
```

## 参数

| 参数        | 含义         | 类型  | 是否必须  |
| ----------- |:-------------:| -----:| -----:|
|text| 显示的文字 | String | true |
