<template>
  <div class="wrapper" ref="aaaa">
    <div>
      <!--   1.无论是否设置click：false，button都能点击   -->
      <button @click="btnClick">按钮</button>

      <!--   2.必须设置click：true，div才能点击   -->
      <div @click="divClick">哈哈哈哈哈</div>
      <ul class="content">
        <button @click="btnClick">你好</button>
        <li>分类列表</li>
        <li>分类列表</li>
        <li>分类列表</li>
        <li>分类列表</li>
        <li>分类列表</li>
        <li>分类列表</li>
        <li>分类列表</li>
        <li>分类列表</li>
        <li>分类列表</li>
        <li>分类列表</li>
        <li>分类列表</li>
        <li>分类列表</li>
        <li>分类列表</li>
        <li>分类列表</li>
        <li>分类列表</li>
        <li>分类列表</li>
        <li>分类列表</li>
        <li>分类列表</li>
        <li>分类列表</li>
        <li>分类列表</li>
        <li>分类列表</li>
        <li>分类列表</li>
        <li>分类列表</li>
        <li>分类列表</li>
        <li>分类列表</li>
        <li>分类列表</li>
        <li>分类列表</li>
        <li>分类列表</li>
        <li>分类列表</li>
        <li>分类列表</li>
        <li>分类列表</li>
        <li>分类列表</li>
        <li>分类列表</li>
        <li>分类列表</li>
        <li>分类列表</li>
        <li>分类列表</li>
        <li>分类列表</li>
        <li>分类列表</li>
        <li>分类列表</li>
        <li>分类列表</li>
        <li>分类列表</li>
        <li>分类列表</li>
        <li>分类列表</li>
        <li>分类列表</li>
        <li>分类列表</li>
        <li>分类列表</li>
        <li>分类列表</li>
        <li>分类列表</li>
        <li>分类列表</li>
        <li>分类列表</li>
        <li>分类列表</li>
        <li>分类列表</li>
        <li>分类列表</li>
        <li>分类列表</li>
        <li>分类列表</li>
        <li>分类列表</li>
      </ul>
    </div>
  </div>
</template>

<script>
  import BScroll from 'better-scroll'
  export default {
    name: "Category",
    data() {
      return {
        scroll: null
      }
    },
    //组件创建完调用
    mounted() {
      this.scroll = new BScroll(document.querySelector('.wrapper'),{
        probeType: 3,
        pullUpLoad: true,
        click: true

      })
      this.scroll.on('scroll',(position) => {
        console.log(position);
      })
      this.scroll.on('pullingUp',() => {
        console.log('上拉加载更多');
        setTimeout(() => {
          this.scroll.finishPullUp()
        },2000)
      })
    },
    methods: {
      btnClick() {
        console.log('btnClick');
      },
      divClick() {
        console.log('divClick');
      }
    }
  }
</script>
<style scoped>
  .wrapper {
    height: 150px;
    background-color: red;
    overflow: hidden;
    /*overflow-y: scroll;*/
  }
</style>
