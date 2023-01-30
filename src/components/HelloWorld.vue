<template>
  <div>
    <div class="wd-top">顶部导航栏</div>
    <div class="wd-content"></div>
    <div class="wd-bottom"></div>
    <div class="wd-sider">
      <div class="wd-sider-list">内容1</div>
      <div class="wd-sider-list">内容2</div>
      <div class="wd-sider-list">内容3</div>
      <div class="wd-sider-list">内容4</div>
      <div class="wd-sider-list">内容5</div>
    </div>
    <div class="wd-back-top" v-if="showBtn" @click="backTop()">回顶部</div>
    
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  data() {
    return {
      showBtn: false,
      ulContent: ["头部内容1", "头部内容2", "头部内容3", "头部内容4", "头部内容5", "头部内容6", "头部内容7"]
    }  
  },
  mounted() {
    window.addEventListener("scroll", this.scrollEvent, true);

  },
  methods: {
    // 回到顶部是否狮子
    scrollEvent() {
      let that = this;
      let scrollTop =
        window.pageYOffset ||
        document.documentElement.scrollTop ||
        document.body.scrollTop;
      console.log('scroll', scrollTop)
      that.scrollTop = scrollTop;
      if (scrollTop > 2000) {
        this.showBtn = true;
      } else {
        this.showBtn = false;
      }
      let header = document.querySelector('.wd-top')
      
      // let styTop = document.querySelector('.wd-top')
      if (that.scrollTop > 60) {
        header.style.background = 'red'
        header.style.top = '0'
      } else {
        header.style.background = 'goldenrod'
        header.style.top = '-90px'
      }
    },

    /*回到顶部实现过程注解：
        1.获取当前页面距离顶部的距离
        2.计算出每次向上移动的距离，用负的滚动距离除以5，因为滚动的距离是一个正数，想向上移动就是一个减法
        3.用当前距离加上计算出的距离，然后赋值给当前距离，就可以达到向上移动的效果
        4.最后在移动到顶部的时候，清除定时器
        */

    backTop() {
      var timer = setInterval(function () {
        let osTop =
          document.documentElement.scrollTop || document.body.scrollTop;
        let ispeed = Math.floor(-osTop / 5);
        document.documentElement.scrollTop = document.body.scrollTop =
          osTop + ispeed;
        this.isTop = true;
        if (osTop === 0) {
          clearInterval(timer);
        }
      }, 30);
    }
  }  
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.wd-before-top{
  width: 100%;
  height: 100px;
  background: goldenrod;
}
.wd-top{ 
  position: fixed;
  top: -80px;
  /*-80px默认情况为隐藏头图，下滑到一定距离再显示*/
  left: 0;
  width: 100%;
  height: 80px;
  background-color: purple;
  text-align: center;
  color: #fff;
  line-height: 80px;
  font-size: 30px;
  transition: all .3s;
}
.wd-sider {
  width: 80px;
  position: fixed;
  right: 4%;
  top: 45%;
  text-align: center;
  line-height: 35px;
  font-size: 25px;
  background-color: rgb(54, 87, 233);
  
  box-shadow: 0px 1px 3px 1px #888888;
  z-index: 999;
}
.wd-sider-list{
  font-size: 5px;
  color: white;
}
.wd-sider-list:hover{
  padding: 0px;
  background: red;
}
 .wd-back-top {
   height: 35px;
   width: 37px;
   position: fixed;
   right: 4%;
   bottom: 11%;
   text-align: center;
   line-height: 35px;
   font-size: 25px;
   background-color: #fff;
   border-radius: 50%;
   box-shadow: 0px 1px 3px 1px #888888;
   z-index: 999;
 }

 
.wd-content{
  width: 100%;
  height: 10000px;
  background: pink;
}
</style>
