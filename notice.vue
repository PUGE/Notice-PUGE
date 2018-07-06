<template>
  <div class="notice-puge-box">
    <div class="item" :style="{top: '0'}">{{copyValue}}</div>
  </div>
</template>

<script>
export default {
  props: {
    text: String
  },
  watch: {
    text (newValue) {
      // 判断
      if (typeof newValue !== 'string') return
      // 判断是否处在动画状态
      if (!this.isAnimation) {
        this.isAnimation = true
        const para = document.createElement("div")
        para.classList.add('item')
        para.style.top = '100%'
        para.innerHTML = newValue
        this.$el.appendChild(para)
        setTimeout(() => {
          this.$el.children[0].style.top = '-100%'
          this.$el.children[1].style.top = '0'
          setTimeout(() => {
            this.$el.removeChild(this.$el.children[0])
            this.isAnimation = false
          }, 500)
        }, 500)
      }
    }
  },
  data () {
    return {
      copyValue: this.text,
      isAnimation: false
    }
  }
}
</script>

<style>
  .notice-puge-box {
    height: 90px;
    line-height: 90px;
    color: #009fe9;
    overflow: hidden;
    font-size: 1.4rem;
    position: relative;
    width: 100%;
  }
  .notice-puge-box .item {
    width: 100%;
    height: 100%;
    position: absolute;
    transition: all 1s;
  }
</style>
